<template>
	<div>
	 <div class="layout-header">白名单管理</div>
	 <div class="layout-content-main">
	 	<Tabs>
	 		 <Tab-pane label="白名单管理">
	 		 	<div><Input v-model="telnum" placeholder="请输入手机号" style="width: 300px"></Input> <Button type="info" @click="soso">搜索</Button></div>
	 		 	<div class="filter">
			 		<Select v-model="place" style="width:200px;margin-right: 40px;" placeholder="全部地区">
		        		<Option v-for="item in placeList" :value="item.value" :key="item">{{ item.label }}</Option>
		    		</Select>
                    <span>开通状态&nbsp;&nbsp;&nbsp;</span>
		    		<Select v-model="status" style="width:200px;margin-right: 40px;" placeholder="全部状态">
		        		<Option v-for="item in statusList" :value="item.value" :key="item">{{ item.label }}</Option>
		    		</Select>
                     <span>支付状态&nbsp;&nbsp;&nbsp;</span>
		    		<Select v-model="paystatus" style="width:200px" placeholder="全部状态">
		        		<Option v-for="item in paystatusList" :value="item.value" :key="item">{{ item.label }}</Option>
		    		</Select>
	 		 	</div>
	 		 	<Table :columns="columns" border  :data="data"></Table>
                  <div class="pageBar">
                  <Page :current="2" :total="50" simple></Page>
                  </div>
	 		 </Tab-pane>
	 	</Tabs>
	 </div>
	 <div class="layout-copy">
            2015-2017 &copy; 找冻品网
        </div>
	</div>
</template>
<script>
    export default {
        data () {
            return {
                place: '',
                placeList: [{ value: 'beijing', label: '北京市'},{value: 'shanghai',label: '上海市'},{value: 'all',label: '全部地区'}],
                status: '',
                statusList: [{ value: 'will', label: '已开通'},{value: 'did',label: '未开通'},{value: 'all',label: '全部状态'}],
                paystatus: '',
                paystatusList: [{ value: 'paid', label: '已支付'},{value: 'pay',label: '未支付'},{value: 'all',label: '全部状态'}],
                columns:[
                    {
                        title: '店铺名',
                        align: 'center',
                        key: 'shop_name'
                    },
                    {
                        title: '地区',
                        align: 'center',
                        key: 'area'
                    },
                    {
                        title: '手机号',
                        align: 'center',
                        key: 'telnum'
                    },
                    {
                        title: '开通状态',
                        align: 'center',
                        key: 'status'
                    },
                    {
                        title: '授信额度(元)',
                        align: 'center',
                        key: 'amount'
                    },
                    {
                        title: '支付状态',
                        align: 'center',
                        key: 'paystatus'
                    },
                    {
                        title: '支付金额(元)',
                        align: 'center',
                        key: 'payamout'
                    }
                ],
                data: [
                	{
                		shop_name: '食品房子',
                		area: '四川',
                		telnum: 100,
                		status: '已开通',
                		amount: 110,
                		paystatus: '已支付',
                		payamout: 990
                	}
                ]
            }
        },
        methods: {
        	soso () {
        		console.log('test');
        	}

        },
        created () {

        }
    }
</script>
<style scoped>
	.filter{margin: 20px 0;}
    .pageBar{float: right;margin-top: 20px;}
</style>