<template>
  <section>
    <el-form :model="editForm"
             :inline="true"
             label-width="100px"
             ref="editForm">
      <el-row>
        <el-col :span="8">
          <el-form-item label="">
            <img :src='editForm.picUrl'
                 style="width: 440px;height: 405px;padding-left:100px;padding-top:10px;margin-bottom:5px;">
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="商品图片链接">
            <el-input size="small"
                      v-model="editForm.picUrl"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="是否备货">
            <el-select size="small"
                       v-model="editForm.stockUp"
                       style="width:390px;">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="商品编码">
            <el-input size="small"
                      v-model="editForm.GoodsCode"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="商品名称">
            <el-input size="small"
                      v-model="editForm.GoodsName"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="中文申报名">
            <el-input size="small"
                      v-model="editForm.AliasCnName"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="英文申报名">
            <el-input size="small"
                      v-model="editForm.AliasEnName"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="采购">
            <el-input size="small"
                      v-model="editForm.Purchaser"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="业绩归属人1">
            <el-input size="small"
                      v-model="editForm.mapPersons"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="责任归属人1">
            <el-input size="small"
                      v-model="editForm.possessMan1"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="供应商名称">
            <el-input size="small"
                      v-model="editForm.SupplierName"
                      style="width:390px;"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="规格">
            <el-select size="small"
                       v-model="editForm.PackName"
                       style="width:390px">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="特殊属性必填">
            <el-select size="small"
                       v-model="editForm.StoreName"
                       style="width:390px">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="仓库">
            <el-select size="small"
                       v-model="editForm.StoreName"
                       style="width:390px">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="季节">
            <el-select size="small"
                       v-model="editForm.Season"
                       style="width:390px">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="描述">
            <el-input size="small"
                      type="textarea"
                      v-model="editForm.description"
                      style="width:1500px"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="关键词Tags">
            <el-input size="small"
                      v-model="editForm.wishtags"
                      style="width: 1500px"
                      placeholder="--tags关键词不能超过10个，逗号分隔--"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="最前关键词">
            <span>
              <font style="color: red">说明：</font>性别定位/多个一卖等。如Women/Men/Girl/Baby/Kids/1PC/2PC/5PC/4 Colors/5Pcs Set…
            </span>
            <br>
            <el-input size="small"
                      v-model="editForm.headKeywords"
                      style="width:1500px"
                      placeholder="--一个关键词--"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="必选关键词">
            <span>
              <font style="color: red">说明：</font>物品名/材质/特征等。如T-Shirt(物品名)/V-neck(特征)/Cotton(材质)
            </span>
            <el-button type="text">批量设置</el-button>
            <div>
              必填
              <el-input size="small"
                        style="width:487px"></el-input>
              <el-input size="small"
                        style="width:487px"></el-input>
              <el-input size="small"
                        style="width:487px"></el-input>
            </div>
            <div>
              选填
              <el-input size="small"
                        style="width:487px"></el-input>
              <el-input size="small"
                        style="width:487px"></el-input>
              <el-input size="small"
                        style="width:487px"></el-input>

            </div>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="随机关键词">
            <span>
              <font style="color: red">说明：</font>形容词/品类热词等。如Fashion/Elegant/Hot/DIY/Casual…
            </span>
            <el-button type="text">批量设置</el-button>
            <div>
              必填
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>
            </div>
            <div>
              选填
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>
              <el-input size="small"
                        style="width:290px"></el-input>

            </div>
          </el-form-item>
        </el-col>
        <el-col :span="24">
          <el-form-item label="最后关键词">
            <span>
              <font style="color: red">说明：</font>附加说明词。如Randomly/S-3XL/2ml/(Color: Nude)/Big Size…
            </span>
            <br>
            <el-input size="small"
                      v-model="editForm.tailKeywords"
                      style="width: 1500px"
                      placeholder="--最多一个关键词--"></el-input>
          </el-form-item>
        </el-col>
      </el-row>
    </el-form>
    <el-form :model="oaGoods"
             :inline="true"
             label-width="100px"
             ref="oaGoods">
      <el-row>
        <el-col :span="6">
          <el-form-item label="禁售平台">
            <el-select size="small"
                       style="width:250px"
                       v-model="editForm.mapPersons">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="6">
          <el-form-item label="主类目">
            <el-select size="small"
                       style="width:250px"
                       v-model="editForm.mapPersons">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="6">
          <el-form-item label="子类目">
            <el-select size="small"
                       style="width:250px"
                       v-model="editForm.mapPersons">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="6">
          <el-form-item label="对应销售">
            <el-select size="small"
                       style="width:250px"
                       v-model="editForm.mapPersons">
              <el-option label="否"
                         value="0"></el-option>
              <el-option label="是"
                         value="1"></el-option>
            </el-select>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="供应商链接1">
            <el-input size="small"
                      v-model="oaGoods.vendor1"
                      style="width:390px"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="供应商链接2">
            <el-input size="small"
                      v-model="oaGoods.vendor2"
                      style="width:390px"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="供应商链接3">
            <el-input size="small"
                      v-model="oaGoods.vendor3"
                      style="width:390px"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="平台链接1">
            <el-input size="small"
                      v-model="oaGoods.origin1"
                      style="width:390px"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="平台链接2">
            <el-input size="small"
                      v-model="oaGoods.origin2"
                      style="width:390px"></el-input>
          </el-form-item>
        </el-col>
        <el-col :span="8">
          <el-form-item label="平台链接3">
            <el-input size="small"
                      v-model="oaGoods.origin3"
                      style="width:390px"></el-input>
          </el-form-item>
        </el-col>
      </el-row>
    </el-form>
    <el-select v-model="btn"
               size="small"
               placeholder="请选择操作方式">
      <el-option v-for="item in options"
                 :key="item.value"
                 :label="item.label"
                 :value="item.value"></el-option>
    </el-select>
    <el-table :data="tableData">
      <el-table-column type="selection"
                       align="center"
                       header-align="center"></el-table-column>
      <el-table-column type="index"
                       align="center"
                       header-align="center">
      </el-table-column>
      <el-table-column label="操作"
                       header-align="center"
                       align="center">
        <template slot-scope="scope">
          <el-tooltip content="删除">
            <i class="el-icon-delete"
               @click="del(scope.$index, scope.row)"
               style="color:#409EFF;cursor:pointer;"></i>
          </el-tooltip>
        </template>
      </el-table-column>
      <el-table-column label="SKU"
                       prop="sku"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.sku"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="款式1"
                       prop="property1"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.property1"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="款式2"
                       prop="property2"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.property2"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="款式3"
                       prop="property3"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.property3"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="成本价"
                       prop="CostPrice"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.CostPrice"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="重量"
                       prop="Weight"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.Weight"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="零售价"
                       prop="RetailPrice"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.RetailPrice"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="joom零售价"
                       prop="joomPrice"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.joomPrice"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="joom运费"
                       prop="joomShipping"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.joomShipping"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="备货数量"
                       prop="stockNum"
                       header-align="center">
        <template slot-scope="scope">
          <el-input size="small"
                    v-model="scope.row.stockNum"></el-input>
        </template>
      </el-table-column>
    </el-table>
    <el-row style="margin-top:5px;">
      <el-col :span="4">
        <el-input v-model="rows"
                  size="small"
                  placeholder="行数"
                  style="width:190px"></el-input>
        <el-button size="small"
                   @click="addClomun">新增行</el-button>
      </el-col>
      <el-col :span="4">
        <el-input v-model="costprice"
                  size="small"
                  placeholder="成本价￥"
                  style="width:190px"></el-input>
        <el-button size="small"
                   @click="cosprice">成本确定</el-button>
      </el-col>
      <el-col :span="4">
        <el-input v-model="weight"
                  size="small"
                  placeholder="重量g"
                  style="width:190px"></el-input>
        <el-button size="small"
                   @click="weht">重量确定</el-button>
      </el-col>
      <el-col :span="4">
        <el-input v-model="retailprice"
                  size="small"
                  placeholder="零售价$"
                  style="width:190px"></el-input>
        <el-button size="small"
                   @click="price">价格确定</el-button>
      </el-col>
      <el-col :span="4">
        <el-input v-model="joomretailprice"
                  size="small"
                  placeholder="joom零售价$"
                  style="width:190px"></el-input>
        <el-button size="small"
                   @click="joomprice">价格确定</el-button>
      </el-col>
      <el-col :span="4">
        <el-input v-model="transportationcost"
                  size="small"
                  placeholder="joom运费$"
                  style="width:185px"></el-input>
        <el-button size="small"
                   @click="transport">价格确定</el-button>
      </el-col>
    </el-row>
    <!-- <div style="margin-top:20px;">
      <el-button size="small"
                 type="success">一键生成SKU</el-button>
      <el-button size="small"
                 type="primary">保存当前数据</el-button>
      <el-button size="small"
                 type="primary">保存并完善</el-button>
      <el-button size="small"
                 type="warning">导入普源</el-button>
      <el-button size="small"
                 type="info">生成采购单</el-button>
      <el-button size="small"
                 type="danger">删除行</el-button>
    </div> -->
    <el-button type="primary"
               @click="save"
               style="position: fixed;bottom: 5px;left:50%;width:200px;">保存</el-button>
  </section>
</template>
<script>
import { APIAttributeInfo, APISaveAttribute } from '../../api/product'
export default {
  data() {
    return {
      tableData: [],
      btn: '',
      rows: null,
      costprice: null,
      weight: null,
      retailprice: null,
      joomretailprice: null,
      transportationcost: null,
      options: [
        {
          value: '选项1',
          label: '一键生成SKU'
        },
        {
          value: '选项2',
          label: '保存当前数据'
        },
        {
          value: '选项3',
          label: '保存并完善'
        },
        {
          value: '选项4',
          label: '导入普源'
        },
        {
          value: '选项5',
          label: '生成采购单'
        },
        {
          value: '选项6',
          label: '删除行'
        }
      ],
      condition: {
        id: 5
      },
      editForm: {},
      oaGoods: {},
      saveInfo: {
        basicInfo: {
          goodsInfo: {
            id: 5,
            IsLiquid: '是',
            IsPowder: '否',
            isMagnetism: '否',
            IsCharged: '否',
            description: null,
            GoodsName: 'test-01-01-plat',
            AliasCnName: null,
            AliasEnName: null,
            PackName: null,
            Season: null,
            DictionaryName: null,
            SupplierName: null,
            StoreName: null,
            Purchaser: null,
            possessMan1: null,
            possessMan2: null,
            DeclaredValue: null,
            picUrl: null,
            goodsid: 24,
            GoodsCode: null,
            achieveStatus: null,
            devDatetime: null,
            developer: null,
            updateTime: null,
            picStatus: null,
            SupplierID: null,
            StoreID: null,
            AttributeName: null,
            bgoodsid: null,
            completeStatus: null,
            isVar: '否',
            headKeywords: null,
            requiredKeywords: null,
            randomKeywords: null,
            tailKeywords: null,
            wishtags: null,
            stockUp: '否',
            picCompleteTime: null,
            goodsstatus: null,
            stockdays: null,
            wishpublish: null,
            number: null,
            mid: null,
            extendStatus: null,
            mapPersons: null,
            filterType: 3
          },
          oaGoods: {
            nid: 24,
            vendor1: '',
            vendor2: null,
            vendor3: null,
            origin1: '',
            origin2: null,
            origin3: null
          }
        },
        skuInfo: [
          {
            id: 1,
            infoId: 5,
            sku: 'jing-a',
            property1: null,
            property2: null,
            property3: null,
            Weight: null,
            memo1: null,
            memo2: null,
            memo3: null,
            memo4: null,
            linkurl: null,
            goodsskuid: null,
            RetailPrice: null,
            CostPrice: null,
            stockNum: null,
            did: null,
            joomPrice: null,
            joomShipping: null
          },
          {
            id: 2,
            infoId: 5,
            sku: 'jingjing-a',
            property1: null,
            property2: null,
            property3: null,
            Weight: null,
            memo1: null,
            memo2: null,
            memo3: null,
            memo4: null,
            linkurl: null,
            goodsskuid: null,
            RetailPrice: null,
            CostPrice: null,
            stockNum: null,
            did: null,
            joomPrice: null,
            joomShipping: null
          },
          {
            id: 3,
            infoId: 5,
            sku: 'jeany-a',
            property1: null,
            property2: null,
            property3: null,
            Weight: null,
            memo1: null,
            memo2: null,
            memo3: null,
            memo4: null,
            linkurl: null,
            goodsskuid: null,
            RetailPrice: null,
            CostPrice: null,
            stockNum: null,
            did: null,
            joomPrice: null,
            joomShipping: null
          },
          {
            id: 4,
            infoId: 5,
            sku: 'jeany-test',
            property1: null,
            property2: null,
            property3: null,
            Weight: null,
            memo1: null,
            memo2: null,
            memo3: null,
            memo4: null,
            linkurl: null,
            goodsskuid: null,
            RetailPrice: null,
            CostPrice: null,
            stockNum: null,
            did: null,
            joomPrice: null,
            joomShipping: null
          },
          {
            id: 5,
            infoId: 5,
            sku: 'jeany-test',
            property1: null,
            property2: null,
            property3: null,
            Weight: null,
            memo1: null,
            memo2: null,
            memo3: null,
            memo4: null,
            linkurl: null,
            goodsskuid: null,
            RetailPrice: null,
            CostPrice: null,
            stockNum: null,
            did: null,
            joomPrice: null,
            joomShipping: null
          }
        ]
      }
    }
  },
  methods: {
    del(index, row) {
      this.tableData.splice(index, 1)
    },
    //增加行
    addClomun() {
      let data = {
        id: null,
        infoId: null,
        sku: '',
        property1: null,
        property2: null,
        property3: null,
        Weight: null,
        memo1: null,
        memo2: null,
        memo3: null,
        memo4: null,
        linkurl: null,
        goodsskuid: null,
        RetailPrice: null,
        CostPrice: null,
        stockNum: null,
        did: null,
        joomPrice: null,
        joomShipping: null
      }
      for (let i = 0; i < this.rows; i++) {
        this.tableData.push(data)
      }
    },
    //成本确定
    cosprice() {
      if (this.costprice) {
        for (let i = 0; i < this.tableData.length; i++) {
          this.tableData[i].CostPrice = this.costprice
        }
      } else {
        return false
      }
    },
    //重量确定
    weht() {
      if (this.weight) {
        for (let i = 0; i < this.tableData.length; i++) {
          this.tableData[i].Weight = this.weight
        }
      } else {
        return false
      }
    },
    //零售价格确定
    price() {
      if (this.retailprice) {
        for (let i = 0; i < this.tableData.length; i++) {
          this.tableData[i].RetailPrice = this.retailprice
        }
      } else {
        return false
      }
    },
    //joom零售价格确定
    joomprice() {
      if (this.joomretailprice) {
        for (let i = 0; i < this.tableData.length; i++) {
          this.tableData[i].joomPrice = this.joomretailprice
        }
      } else {
        return false
      }
    },
    //joom运费
    transport() {
      if (this.transportationcost) {
        for (let i = 0; i < this.tableData.length; i++) {
          this.tableData[i].joomShipping = this.transportationcost
        }
      } else {
        return false
      }
    },
    save() {
      APISaveAttribute(this.saveInfo).then(res => {
        if (res.data.data[0] === 'success') {
          this.$message({
            message: '保存成功',
            type: 'success'
          })
        } else {
          this.$message.error('保存失败')
        }
      })
    },
    getData() {
      APIAttributeInfo(this.condition).then(res => {
        this.tableData = res.data.data.skuInfo
        this.editForm = res.data.data.basicInfo.goodsInfo
        this.oaGoods = res.data.data.basicInfo.oaGoods
      })
    }
  },
  mounted() {
    // this.condition.id = this.$route.params.id
    this.getData()
  }
}
</script>
<style lang="scss" scoped>
section {
  margin-bottom: 80px;
}
</style>

