<template>
<div>
    <div class="base">
        <div class="block buttonClass">
            <span class="wrapper">
                <el-button type="success"><router-link to="/example/SpiderAdd">添加</router-link></el-button>
                <el-button type="warning" @click="del()" >删除</el-button>
            </span>
        </div>
    </div>
    <div>

        <el-table
          ref="multipleTable"
          :data="tableData3"
          border
          tooltip-effect="dark"
          style="width: 100%"
          @selection-change="handleSelectionChange">
          <el-table-column
            type="selection"
            width="55">
          </el-table-column>
          <el-table-column
            label="网站名称"
            width="120">
            <template scope="scope">{{ scope.row.webSizeName }}</template>
          </el-table-column>
          <el-table-column
            prop="address"
            label="网址"
            width="120">
          </el-table-column>
          <el-table-column
            prop="number"
            label="数据量"
            show-overflow-tooltip>
          </el-table-column>
           <el-table-column
            fixed="right"
            label="操作"
            width="150">
            <template scope="scope">
                <el-button type="text" size="small">修改配置</el-button>
                <el-button @click="handleClick" type="text" size="small">运行</el-button>
            </template>
            </el-table-column>
        </el-table>
    </div>

    <div class="block page">
      <!-- 分页暂时有问题 -->
      <el-pagination
        @size-change="handleSizeChange"
        @current-change="handleCurrentChange"
        :current-page="currentPage4"
        :page-sizes="[100, 200, 300, 400]"
        :page-size="100"
        layout="total, sizes, prev, pager, next, jumper"
        :total="400">
      </el-pagination>
    </div>

</div>
</template>

<script>
  export default {
    data() {
      return {
        tableData3: [{
          webSizeName: '2016-05-03',
          address: '王小虎',
          number: '上海市普陀区金沙江路 1518 弄'
        }, {
          webSizeName: '2016-05-02',
          address: '王小虎',
          number: '上海市普陀区金沙江路 1518 弄'
        }, {
          webSizeName: '2016-05-04',
          address: '王小虎',
          number: '上海市普陀区金沙江路 1518 弄'
        }, {
          webSizeName: '2016-05-01',
          address: '王小虎',
          number: '上海市普陀区金沙江路 1518 弄'
        }, {
          webSizeName: '2016-05-08',
          address: '王小虎',
          number: '上海市普陀区金沙江路 1518 弄'
        }, {
          webSizeName: '2016-05-06',
          address: '王小虎',
          number: '上海市普陀区金沙江路 1518 弄'
        }, {
          webSizeName: '2016-05-07',
          address: '王小虎',
          number: '上海市普陀区金沙江路 1518 弄'
        }],
        multipleSelection: []
      }
    },

    methods: {
      del() {
        var delteVal = this.multipleSelection;
              if(delteVal.length==0){
                this.$message({
                showClose: true,
                message: '没有选择任何数据哦',
                type: 'warning'
              }); 
          }
          for(var i = 0 ;i < delteVal.length ;i++){
            //拼装数据传输后台
            alert(delteVal[i].address);
          };
      },
      toggleSelection(rows) {
        if (rows) {
          rows.forEach(row => {
            this.$refs.multipleTable.toggleRowSelection(row);
          });
        } else {
          this.$refs.multipleTable.clearSelection();
        }
      },
      handleSelectionChange(val) {
        this.multipleSelection = val;
      },
      handleClick() {
        console.log(1);
      }
    }
  }
</script>


<style scoped>
    .buttonClass {
       margin: 50px 0 40px 514px;
    }
    .page {
        margin-top: 10px;
        margin-right: 0;
    }

</style>
