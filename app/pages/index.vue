<template>
  <div>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="date" label="Date" width="180" />
      <el-table-column prop="name" label="Name" width="180" />
      <el-table-column prop="address" label="Address" />
    </el-table>

    <el-button type="primary" @click="dialogFormVisible = true" class="mt-5"
      >添加书籍</el-button
    >

    <el-dialog v-model="dialogFormVisible" title="新增书籍" width="500">
      <el-form :model="form" label-width="auto" style="max-width: 600px">
        <el-form-item label="书名">
          <el-input v-model="form.name" />
        </el-form-item>

        <el-form-item label="持续时间">
          <el-date-picker
            v-model="form.duringtime"
            type="daterange"
            single-panel
            range-separator="-"
            start-placeholder="开始"
            end-placeholder="结束"
          />
        </el-form-item>

        <el-form-item label="状态">
          <el-radio-group v-model="form.status">
            <el-radio value="已读">已读</el-radio>
            <el-radio value="未读">未读</el-radio>
            <el-radio value="闲置">闲置</el-radio>
          </el-radio-group>
        </el-form-item>
      </el-form>

      <template #footer>
        <div class="dialog-footer">
          <!-- <el-button @click="dialogFormVisible = false">取消</el-button> -->
          <el-button type="primary" @click="dialogFormVisible = false">
            确定
          </el-button>
        </div>
      </template>
    </el-dialog>
  </div>
</template>

<script lang="ts" setup>
useHead({
  title: "记录一切 - 主页",
});

const dialogFormVisible = ref(false);

// do not use same name with ref
const form = reactive({
  name: "",
  duringtime: "",
  status: "",
});

const tableData = [
  {
    date: "2016-05-03",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-02",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-04",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
  {
    date: "2016-05-01",
    name: "Tom",
    address: "No. 189, Grove St, Los Angeles",
  },
];
</script>
