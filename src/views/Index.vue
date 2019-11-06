<template>
  <div id="index">
    <el-row :gutter="20">
      <el-col v-for="item in tableData" :key="item.guid" :xs="20" :sm="10" :md="8" :lg="6" :xl="4">
        <el-card class="box-card">
          <span class="projectStatus">{{item.projectStatus | formStatus}}</span>
          <img :src="item.logo | formImg" alt="logo" />
          <div class="cart-text">
            <ul>
              <li>
                <h3 v-text="item.prjName"></h3>
              </li>
              <li>
                项目经理：
                <span v-text="item.prjManager"></span>
              </li>
              <li>
                立项日期：
                <span>{{item.prjStartDate | formatDate}}</span>
              </li>
              <li>
                <span>任务：{{item.taskCount}}</span>
                <span>完成:{{item.taskDoneCount}}</span>
                <span>进行:{{item.taskDoingCount}}</span>
              </li>
            </ul>
          </div>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [
        {
          productCategory: "家教机",
          prjCategory: "教育电子软件产品开发项目",
          prjName: "测试项目密码",
          prjManager: "孙工",
          prjStartDate: "2018-08-04 18:34:58",
          prjEndDate: "2018-08-28 18:34:58",
          guid: "a6d6e2d1-ea1f-47de-aec7-4397bc74bfcd",
          projectStatus: "processing",
          department: "系统管理部",
          logo: "image.png",
          taskCount: 0,
          taskDoneCount: 0,
          taskDoingCount: 0
        },
        {
          productCategory: "电话手表",
          prjCategory: "电话手表产品开发项目",
          prjName: "集成测试0712",
          prjManager: "孙工,郑工",
          prjStartDate: "2018-08-04 18:34:58",
          prjEndDate: "2018-08-28 18:34:58",
          guid: "4be3d93b-b901-462d-b87e-d17548597ab6",
          projectStatus: "processing",
          department: "系统管理部",
          logo: "image.png",
          taskCount: 0,
          taskDoneCount: 0,
          taskDoingCount: 0
        },
        {
          productCategory: "其他",
          prjCategory: "IT项目",
          prjName: "testRead",
          prjManager: "孙工",
          prjStartDate: "2018-08-06 20:56:23",
          prjEndDate: "2018-08-31 20:56:23",
          guid: "0508420c-ecc4-4cc3-9b21-3b5256874221",
          projectStatus: "approving",
          department: "系统管理部",
          logo: "image.png",
          taskCount: null,
          taskDoneCount: null,
          taskDoingCount: null
        },
        {
          productCategory: "其他",
          prjCategory: "产品预研项目",
          prjName: "任务直接完成",
          prjManager: "孙工",
          prjStartDate: "2018-07-30 16:40:03",
          prjEndDate: "2018-07-30 16:40:03",
          guid: "b4fdc9d4-dc8a-4190-b16c-d5c0f3feb379",
          projectStatus: "processing",
          department: "系统管理部",
          logo: "image.png",
          taskCount: 14,
          taskDoneCount: 13,
          taskDoingCount: 1
        },
        {
          productCategory: "其他",
          prjCategory: "测试",
          prjName: "aab1216",
          prjManager: "孙工",
          prjStartDate: "2018-07-30 16:40:03",
          prjEndDate: "2018-07-30 16:40:03",
          guid: "c6ae03d5-b90b-41da-9103-7463fa61a6f3",
          projectStatus: "processing",
          department: "系统管理部",
          logo: "image.png",
          taskCount: 1,
          taskDoneCount: 0,
          taskDoingCount: 1
        }
      ]
    };
  },
  filters: {
    formatDate(value) {
      return value.split(" ")[0];
    },
    formImg() {
      return require("@/assets/image.png");
    },
    formStatus(value) {
      switch (value) {
        case "processing":
          return "进行中";
        case "approving":
          return "通过";
      }
    }
  }
};
</script>

<style>
.text {
  font-size: 14px;
}

ul {
  list-style: none;
}
.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}
.clearfix:after {
  clear: both;
}
.el-col {
  margin-bottom: 20px;
}
.el-card__body::before,
.el-card__body::after {
  content: "";
  height: 0;
  line-height: 0;
  display: block;
  visibility: hidden;
  clear: both;
}
.el-card__body:after {
  clear: both;
}
.el-card__body {
  *zoom: 1;
  display: flex;
  height: 150px;
  position: relative;
}
.el-card__body img {
  display: inline-block;
  width: 50px;
  height: 50px;
}
.cart-img {
  width: 20%;
}
.cart-text ul h3 {
  font-weight: normal;
  line-height: 30px;
  font-size: 16px;
  margin: 0;
  width: 80%;
}
.cart-text ul span {
  line-height: 30px;
  font-size: 16px;
}
.projectStatus {
    position:absolute;
    right: 10px;
    top: 10px;
}
</style>