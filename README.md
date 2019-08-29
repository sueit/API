
#### 1.1 版本历史
| 日期 | 版本号 | 作者 | 备注 |
| ------------ | ----------- | ----------- | ----------- |
| 2019-08-28 | v1.0.1 | Aprils | 第一版 |


#### 1.2 接口统一返回格式
- 正常返回
```xml
{
  "code": 200,
  "message": "操作成功",
  "result": 某种类型的数据，如：字符串、数字、布尔值、集合等
}
```
- 校验参数错误返回
```xml
{
  "code": 100,
  "message": "参数非法 + 具体错误信息说"
}
```
- 错误返回
```xml
{
  "code": 500,
  "message": "错误信息"
}
```


















#### 1.3 接口
#### 接口说明：获取合同列表页
 请求方法：GET
 请求URL：/api/contractList
 请求参数格式：

| 参数 | 参数类型 | 参数名称 |
|:----:|:----:|:----:|
| type | Int | 列表状态 (0 全部合同  1 未完成 2已完成）（必填） |
| page | Int | 页码(从0开始)（必填） |
| size | Int | 每页数据条数（必填） |

返回参数：

| 参数名称   |    |    | 参数类型   | 参数名称   |
|:----|:----|:----|:----|:----|
| code   |    |    | Int  200 操作成功 100 参数非法 500 错误信息   | 是否成功   |
| result   |    |    | List   |    |
|    | user   |    | Object   | 客户信息   |
|    |    | customerId   | Int   | 客户编号   |
|    |    | customerName   | String   | 客户名   |
|    | content   |    | Object   | 合同信息   |
|    |    | contractId | Int | 合同号id |
|    |    | contractName | String | 合同名 |
|    |    | contractImg | String | 合同图片地址 |
|    |    | orderAllId | Int | 客户订单号（是否有一个汇总的客户订单号？没有就删除） |
|    |    | pipeWeight |    | 合同下钢管总重量(/kg) |
|    |    | shippedWeight | Float | 已发钢管重量(/kg) |
|    |    | unshippedWeight | Float | 未发钢管重量(/kg) |
|    |    | signingDate | String | 签单日期 |
|    |    | deliveryDate | String | 交货日期 |
|    |    | daysRemaining | Int | 剩余天数 |
|    |    | rateProgress | String | 合同总进度 |
|    |    | amount | Int | 总金额 |
|    |    | isComplete | Int | 是否完成 0 否 1 是 |
| message   |    |    | String | 反馈提示信息 |









#### 接口说明：获取合同详情页
请求方法：GET
请求URL：/api/contractDetail
请求参数格式：

| 参数 | 参数类型 | 参数名称 |
|:----:|:----:|:----:|
| contractId | Int | 合同号id （必填）|

返回参数：

| 参数名称   |    |    | 参数类型   | 参数名称   |
|:----|:----|:----|:----|:----|
| code   |    |    | Int 200 操作成功 100 参数非法 500 错误信息   | 是否成功   |
| result   |    |    | Object   |    |
|    | detail   |    | Object   | 合同信息   |
|    |    | contractId | Int | 合同号id |
|    |    | contractName | String | 合同名 |
|    |    | contractImg | String | 合同图片地址 |
|    |    | orderAllId | Int | 客户订单号（是否有一个汇总的客户订单号？没有就删除） |
|    |    | pipeWeight |    | 合同下钢管总重量(/kg) |
|    |    | shippedWeight | Float | 已发钢管重量(/kg) |
|    |    | unshippedWeight | Float | 未发钢管重量(/kg) |
|    |    | signingDate | String | 签单日期 |
|    |    | deliveryDate | String | 交货日期 |
|    |    | daysRemaining | Int | 剩余天数 |
|    |    | rateProgress | String | 合同总进度 |
|    |    | amount | Int | 总金额 |
|    |    | salesContacts | String | 销售联系人 |
|    |    | salesTel | Int | 联系人电话 |
|    | orderList   |    | List |    |
|    |    | orderId | Int | 客户订单号 |
|    |    | orderName | String | 客户订单名 |
|    |    | orderImg | String | 订单图片 |
|    |    | orderProgress | Int | 订单进度 |
|    |    | isComplete | Int | 是否完成 0 否 1 是 |
| message   |    |    | String | 反馈提示信息 |








#### 接口说明：获取订单详情页
请求方法：GET
请求URL：/api/orderDetail
请求参数格式：

| 参数 | 参数类型 | 参数名称 |
|:----:|:----:|:----:|
| orderId | Int | 客户订单号id （必填）|

返回参数：

| 参数名称   |    |    |    |    |    | 参数类型   | 参数名称   |  
|:----|:----|:----|:----|:----|:----|:----|:------------|
| code   |    |    |    |    |    | Int 200 操作成功 100 参数非法 500 错误信息   | 是否成功   |  
| result   |    |    |    |    |    | Object   |    |    |   
|    | detail   |    |    |    |    | Object   | 合同信息   |   
|    |    | orderId |    |    |    | Int | 客户订单号id |    |   
|    |    | orderName |    |    |    | String | 客户订单名 |   
|    |    | orderImg |    |    |    | String | 订单图片地址 |   
|    |    | orderAllId |    |    |    | Int | 客户订单号（是否有一个汇总的客户订单号？没有就删除） |   
|    |    | pipeNum |    |    |    | Int | 钢管支数 |  
|    |    | pipeLength |    |    |    | Float | 钢管长度 |  
|    |    | pipeSpecification |    |    |    | String | 钢管规格 |    
|    |    | pipeStandard |    |    |    | String | 钢管标准 |  
|    |    | pipeWeight |    |    |    | Float | 订单下钢管总重量(/kg) |   
|    |    | shippedWeight |    |    |    | Float | 已发钢管重量(/kg) |   
|    |    | unshippedWeight |    |    |    | Float | 未发钢管重量(/kg) |  
|    |    | signingDate |    |    |    | String | 签单日期 |    
|    |    | deliveryDate |    |    |    | String | 交货日期 |   
|    |    | daysRemaining |    |    |    | Int | 剩余天数 |   
|    |    | rateProgress |    |    |    | String | 订单进度 |   
|    |    | unitPrice |    |    |    | Int | 单价(/kg) |    
|    |    | amount |    |    |    | Int | 总金额 |    
|    | trackingRecords   |    |    |    |    | Object |   
|    |    | Step1 |    |    |    | Object | 订单跟踪记录-物料采购订单 |  
|    |    |    | isWork |    |    | Int | 是否正在进行  0 否 1 是 |   
|    |    |    | stepName |    |    | String | 跟踪记录名称 |   
|    |    |    | stepDate |    |    | String | 跟踪记录时间 |  
|    |    |    | progress |    |    | Int | 进度百分比 |   
|    |    | Step2 |    |    |    |    | 订单跟踪记录-物料质检入库 |   
|    |    |    | isWork |    |    | Int | 是否正在进行  0 否 1 是 |   
|    |    |    | stepName |    |    | String | 跟踪记录名称 |  
|    |    |    | stepDate |    |    | String | 跟踪记录时间 |   
|    |    |    | progress |    |    | Int | 进度百分比 |   
|    |    |    | certificateGuarantee   |    |    | Object   | 质保书内容   |   
|    |    | Step3 |    |    |    |    | 订单跟踪记录-物料质检入库 |   
|    |    |    | isWork |    |    | Int | 是否正在进行  0 否 1 是 |   
|    |    |    | stepName |    |    | String | 跟踪记录名称 |    
|    |    |    | stepDate |    |    | String | 跟踪记录时间 |    
|    |    |    | progress |    |    | Int | 进度百分比 |   
|    |    |    | productionList |    |    | List | 框列表 |  
|    |    |    |    | frameNum |    | Int | 框数（1,2,3...） |  
|    |    |    |    | pipeNumber |    | Int | 钢管数量 |  
|    |    |    |    | pipeSpecification |    | String | 钢管规格 |   
|    |    |    |    | oneWeight |    | Float | 单支钢管重量(/kg) |  
|    |    |    |    | procedureList |    | List | 道次列表 |  
|    |    |    |    |    | procedureName | Int | 道次数（1,2,3...） |   
|    |    |    |    |    | isWork | Int | 是否正在进行  0 否 1 是 |    
|    |    | Step4 |    |    |    |    | 订单跟踪记录-成品质检  |   
|    |    |    | isWork |    |    | Int | 是否正在进行  0 否 1 是 |  
|    |    |    | stepName |    |    | String | 跟踪记录名称 |   
|    |    |    | stepDate |    |    | String | 跟踪记录时间 |  
|    |    |    | progress |    |    | Int | 进度百分比 |    
|    |    |    | certificateGuarantee   |    |    | Object   | 质保书内容   |    
|    |    | Step5 |    |    |    |    | 订单跟踪记录-成品出厂  |  
|    |    |    | isWork |    |    | Int | 是否正在进行  0 否 1 是 |   
|    |    |    | stepName |    |    | String | 跟踪记录名称 |   
|    |    |    | stepDate |    |    | String | 跟踪记录时间 |   
|    |    |    | progress |    |    | Int | 进度百分比 |   
|    |    |    | logisticsInformation   |    |    | List   | 物流信息   |   
|    |    | Step6 |    |    |    |    | 订单跟踪记录-客户签收  |   
|    |    |    | stepName |    |    | String | 跟踪记录名称 |  
|    |    |    | stepDate |    |    | String | 跟踪记录时间 |   
| message   |    |    |    |    |    | String | 反馈提示信息 |   
