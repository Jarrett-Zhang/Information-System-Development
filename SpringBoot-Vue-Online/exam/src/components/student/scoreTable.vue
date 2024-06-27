//显示学生成绩
<template>
  <div class="table">
    <p class="title">我的分数</p>
    <section class="content-el">
      <el-table ref="filterTable" :data="score" v-loading="loading">
        <el-table-column
          prop="answerDate"
          label="考试日期"
          sortable
          width="300"
          column-key="answerDate"
          :filters="filter"
          :filter-method="filterHandler">
        </el-table-column>
        <el-table-column
          prop="subject"
          label="课程名称"
          width="300"
          filter-placement="bottom-end">
          <template slot-scope="scope">
            <el-tag>{{scope.row.subject}}</el-tag>
          </template>
        </el-table-column>
        <el-table-column prop="etScore" label="考试分数" width="200"></el-table-column>
        <el-table-column label="是否及格" width="100">
          <template slot-scope="scope">
            <el-tag :type="scope.row.etScore>= 60 ? 'success' : 'danger'">{{scope.row.etScore >= 60 ? "及格" : "不及格"}}</el-tag>
          </template>
        </el-table-column>
      </el-table>
      <el-row type="flex" justify="center" align="middle" class="pagination">
        <el-pagination
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
          :current-page="pagination.current"
          :page-sizes="[4,6,8,10]"
          :page-size="pagination.size"
          layout="total, sizes, prev, pager, next, jumper"
          :total="pagination.total">
        </el-pagination>
      </el-row>
    </section>
  </div>
</template>


<style lang="less" scoped>
.pagination {
  padding-top: 20px;
}
.table {
  width: 980px;
  margin: 0 auto;
  .title {
    margin: 20px;
  }
  .content-el {
    background-color: #fff;
    padding: 20px;
  }
}
</style>
