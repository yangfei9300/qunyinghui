<template>
	<view>
		<view class="colonn">
			<image @load="imgload($event,1)" src="../../static/datitop.jpg" mode="widthFix" class="w-750"></image>
			<view class="colonn w-750 cenbterbg  center_center" :style="{
				'height':(screenHeightPx-img1-img2)+'rpx'
			}">
				<scroll-view scroll-y :style="{
					'height':(screenHeightPx-img1-img2)+'rpx'
				}">
					<view class="colonn p-all-30">
						<view class="h-50"></view>
						<view class="roww center_center duiqi">
							<view class="fs-40 fw-800">批阅中</view>
						</view>
						<view class="h-50"></view>
						<!-- <view class="colonn fs-40 w-690">
							<view>极大规模集成电路间李春雷虽上的佛龛歌城是极大规模集成电路间李春雷虽上的佛龛歌城是极大规模集成电路间李春雷虽上的佛龛歌城是(简单题)</view>
						</view>
						<view class="h-60"></view> -->

						<!-- <view class="roww fs-40">
							<view>作答队伍：A队</view>
						</view>
						<view class="h-15"></view>
						<view class="roww fs-40">
							<view>作答队员：江女士</view>
						</view>
						<view class="h-60"></view> -->
						<!-- <view>
							<text class="fw-800">作答内容：</text>
							收到了发咯水电费记录卡师大暨大是落实贷款封建时代联防联控水电费收到了副科级第三方离开
							收到了发咯水电费记录卡师大暨大是落实贷款封建时代联防联控水电费收到了副科级第三方离开
						</view>
						<view class="h-40"></view> -->

						<block>

							<view class="fs-40 fw-800">案例分析打分（总分100分）</view>
							<view class="h-20"></view>

							<view class="colonn center_center">
								<view class="fs-40 w-690">1.根据影像学资料给出正确的病例诊断结果：</view>
								<view class="h-20"></view>
								<input type="number" class="textawa" v-model="fens.fen1"
									@input="isFenSubChange($event,0)" placeholder="最高30分"></input>
								<view 
								class="roww w-650" 
								style="color:red;" 
								v-if="!isFenSub[0]"
								>
									<view>最高分{{fenBz[0]}}分</view>
									<view class="allline"></view>
								</view>
							</view>
							<view style="color: red;" v-if="!heTishi[0]">第1项得分必须大于等于25小于30</view>
							<view class="h-20"></view>
							<view class="colonn center_center">
								<view class="fs-40 w-690">2.诊断思路阐述逻辑清晰有条理，表述完整精炼，重点突出：</view>
								<view class="h-20"></view>
								<input type="number" class="textawa" v-model="fens.fen2"
									@input="isFenSubChange($event,1)" placeholder="最高30分"></input>
									<view
									class="roww w-650" 
									style="color:red;" 
									v-if="!isFenSub[1]"
									>
										<view>最高分{{fenBz[1]}}分</view>
										<view class="allline"></view>
									</view>
							</view>
							<view style="color: red;"  v-if="!heTishi[1]">第2项得分必须大于等于25小于30</view>
							<view class="h-20"></view>
							<view class="colonn center_center">
								<view class="fs-40 w-690">3.含有针对性的鉴别诊断，鉴别诊断结合病人具体病情：</view>
								<view class="h-20"></view>
								<input type="number" class="textawa" v-model="fens.fen3"
									@input="isFenSubChange($event,2)" placeholder="最高20分"></input>
									<view
									class="roww w-650" 
									style="color:red;" 
									v-if="!isFenSub[2]"
									>
										<view>最高分{{fenBz[2]}}分</view>
										<view class="allline"></view>
									</view>
							</view>
							<view class="h-20"></view>
							<view class="colonn center_center">
								<view class="fs-40 w-690">4.如可能，提出进一步诊断方案：</view>
								<view class="h-20"></view>
								<input type="number" class="textawa" v-model="fens.fen4"
									@input="isFenSubChange($event,3)" placeholder="最高10分"></input>
									
									<view
									class="roww w-650" 
									style="color:red;" 
									v-if="!isFenSub[3]"
									>
										<view>最高分{{fenBz[3]}}分</view>
										<view class="allline"></view>
									</view>
									
							</view>
							
							<view style="color: red;"  v-if="!heTishi[2]">第3,4项得分之和必须大于等于25小于等于30</view>
							
							<view class="h-20"></view>
							<view class="colonn center_center">
								<view class="fs-40  w-690">5.语言表达清晰完整，声音洪亮，语速和节奏适中：</view>
								<view class="h-20"></view>
								<input type="number" class="textawa" v-model="fens.fen5"
									@input="isFenSubChange($event,4)" placeholder="最高5分"></input>
									
									<view
									class="roww w-650" 
									style="color:red;" 
									v-if="!isFenSub[4]"
									>
										<view>最高分{{fenBz[4]}}分</view>
										<view class="allline"></view>
									</view>
									
							</view>
							<view class="h-20"></view>
							<view class="colonn center_center">
								<view class="fs-40  w-690">6.PPT制作规范，排版美观（5分）：</view>
								<view class="h-20"></view>
								<input type="number" class="textawa" v-model="fens.fen6"
									@input="isFenSubChange($event,5)" placeholder="最高5分"></input>
									<view
									class="roww w-650" 
									style="color:red;" 
									v-if="!isFenSub[5]"
									>
										<view>最高分{{fenBz[5]}}分</view>
										<view class="allline"></view>
									</view>
							</view>
							<view style="color: red;"  v-if="!heTishi[3]">第5,6项得分之和必须大于等于5小于10</view>
							
							<view class="h-20"></view>

							<view class="h-100"></view>
							<view class="fs-40 fw-800">补充回答质量（总分20分）</view>
							<view class="h-50"></view>
							
							<!-- <view class="fs-40">作答队伍：<text class="fs-40">B队</text></view>
							<view class="h-20"></view>
							<view class="roww fs-40">
							<view>作答队员：</view>
							<view class="">江女士 </view>
							</view> -->
							<view class="h-20"></view>
							<view class="colonn center_center">
								<view class="fs-40  w-690">1.有效补充答题队缺失的内容：</view>
								<view class="h-20"></view>
								<input 
								
								type="number" 
								class="textawa" 
								v-model="fens.fen7" 
								@input="isFenSubChange($event,6)"
								placeholder="最高10分"
									></input>
									
								<view
									class="roww w-650" 
									style="color:red;" 
									v-if="!isFenSub[6]"
									>
										<view>最高分{{fenBz[6]}}分</view>
										<view class="allline"></view>
								</view>
									
							</view>
							<view class="h-20"></view>
							<view class="colonn center_center">
								<view class="fs-40  w-690">2.诊断思路阐述逻辑清晰合理，重点突出：</view>
								<view class="h-20"></view>
								<input type="number" class="textawa" 
								v-model="fens.fen8" 
								@input="isFenSubChange($event,7)"
									placeholder="最高10分"></input>
								
								<view
									class="roww w-650" 
									style="color:red;" 
									v-if="!isFenSub[7]"
									>
										<view>最高分{{fenBz[7]}}分</view>
										<view class="allline"></view>
								</view>	
								
							</view>
						</block>
						<view class="h-40"></view>
						<view class="btns1" @click.stop="toSubmit">提交</view>
					</view>
				</scroll-view>
			</view>
			<image @load="imgload($event,2)" src="../../static/datibottom.jpg" mode="widthFix" class="w-750"></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				'screenHeightPx': 0,
				img1: 0,
				img2: 0,
				startTime: 0, //开始的时间戳
				nowTime: 0,
				miaoshu: 30, //倒计时
				tiIndex: 1,

				numberInput: '',
				formattedNumber: '',
				duiyuans: ['江女士1', '江女士2', '江女士3'],

				fens: {
					'fen1': '',
					'fen2': '',
					'fen3': '',
					'fen4': '',
					'fen5': '',
					'fen6': '',
					'fen7': '',
					'fen8': '',
				},
				isFenSub: [
					true, true, true, true, true, true, true, true, true
				],
				form: {
					'score_str': '',
					'score': '',
					'b1score_str': '',
					'b1score': '',
					'uuid': ''
				},
				fenBz : [30, 30, 20, 10, 5, 5, 10, 10],
				
				heTishi:[true,true,true,true],
				
			}
		},
		onLoad() {
			// 获取当前界面的宽高
			const systemInfo = uni.getSystemInfoSync();
			const screenWidth = systemInfo.screenWidth;
			const screenHeight = systemInfo.screenHeight;
			console.log("屏幕的原始高", )
			const bili = 750 / screenWidth;
			const screenHeightPx = bili * screenHeight;
			this.screenHeightPx = screenHeightPx;
		},
		methods: {
			heTishiSUb(){
				
				if(this.fens.fen1!=""){
					if(this.fens.fen1<25||this.fens.fen1>30){
						this.heTishi[0]=false;
					}else{
						this.heTishi[0]=true;
					}
				}
				
				if(this.fens.fen2!=""){
					if(this.fens.fen2<25||this.fens.fen2>30){
						this.heTishi[1]=false;
					}else{
						this.heTishi[1]=true;
					}
				}
				console.log("000",this.fens.fen3,this.fens.fen4)
				if(this.fens.fen3!=""&&this.fens.fen4!=""){
					var he=parseFloat(this.fens.fen3)+parseFloat(this.fens.fen4);
					console.log("合一块",he)
					if(he<25||he>30){
						this.heTishi[2]=false;
					}else{
						this.heTishi[2]=true;
					}
				}
				if(this.fens.fen5!=""&&this.fens.fen6!=""){
					var he=parseFloat(this.fens.fen5)+parseFloat(this.fens.fen6);
					if(he<5||he>10){
						this.heTishi[3]=false;
					}else{
						this.heTishi[3]=true;
					}
				}
				this.$forceUpdate()
			},
			// 这分是否可以提交
			isFenSubChange(res, index) {
				var value = res.detail.value;
				var fenBz = [30, 30, 20, 10, 5, 5, 10, 10];
				if (value != "") {
					value = parseFloat(value)
					if (value > fenBz[index]) {
						
						this.isFenSub[index] = false;
					}else{
						this.isFenSub[index] = true;
					}
				}else{ 
					if(index<6){
						this.isFenSub[index] = false;
					}else{
						this.isFenSub[index] = true;
					}
					
				}
				this.heTishiSUb();
			},
			// 提交
			toSubmit() {
				if (!this.isSubmit()) {
					return false;
				}
				// timuList[a].fen=parseFloat(timuList[a].fen).toFixed(1);
				var fens = this.fens;
				fens.fen1 = parseFloat(fens.fen1).toFixed(1);
				fens.fen2 = parseFloat(fens.fen2).toFixed(1);
				fens.fen3 = parseFloat(fens.fen3).toFixed(1);
				fens.fen4 = parseFloat(fens.fen4).toFixed(1);
				fens.fen5 = parseFloat(fens.fen5).toFixed(1);
				fens.fen6 = parseFloat(fens.fen6).toFixed(1);
				fens.fen7 = parseFloat(fens.fen7).toFixed(1);
				fens.fen8 = parseFloat(fens.fen8).toFixed(1);
				var score = parseFloat(fens.fen1) + parseFloat(fens.fen2) + parseFloat(fens.fen3) + parseFloat(fens.fen4) +
					parseFloat(fens.fen5) + parseFloat(fens.fen6);
				var b1score = parseFloat(fens.fen7) + parseFloat(fens.fen8);
				var form = {
					'score_str': fens.fen1 + "," + fens.fen2 + "," + fens.fen3 + "," + fens.fen4 + "," + fens.fen5 +
						"," + fens.fen6,
					'score': score.toFixed(1),
					'b1score_str': fens.fen7 + "," + fens.fen8,
					'b1score': b1score.toFixed(1),
					'uuid': uni.getStorageSync("userId")
				}

				this.$axios
					.axios('POST', this.$paths.markPut, form)
					.then(res => {
						if (res.code == 1) {
							console.log("阿斯顿", res);
							this.$tools.showToast("提交成功");
							setTimeout(res => {
								uni.navigateBack({
									delta: 1
								})
							}, 1000)
						} else {
							this.$tools.showToast(res.info)
						}
					})
					.catch(err => {
						console.log('错误回调', err);
					});

			},
			isSubmit() {
				
				
				
				
				if (this.fens.fen1 == "" || this.fens.fen2 == "" || this.fens.fen3 == "" ||
					this.fens.fen4 == "" || this.fens.fen5 == "" || this.fens.fen6 == ""
				) {
					this.$tools.showToast("有遗漏未打分，提交失败");
					return false;
				}
				var isFenSub=this.isFenSub;
				var count=0;
				for(var a=0;a<isFenSub.length;a++){
						if(!isFenSub[a]){
							count=count+1;
						}
				}
				
				if(count>0){
					this.$tools.showToast("有部分打分不规范，提交失败");
					return false;
				}
				var isYes=0;
				for(var a=0;a<this.heTishi.length;a++){
					if(!this.heTishi[a]){
						isYes=isYes+1;
					}
				}
				if(isYes>0){
					this.$tools.showToast("有部分打分不规范，提交失败");
					return false;
				}
			
				
				return true;
			},


			checkPrice(e) {
				var value = e.detail.value;
				this.$nextTick(() => {
					//'有小数点时，最大长度为7位，没有则是5位'
					this.numberInput = value
				})
			},

			// 下一题点击事件
			nextQuestion() {
				if (this.tiIndex == 10) {
					this.tiIndex = 11
					this.$tools.showToast("打分完成");
					setTimeout(res => {
						uni.redirectTo({
							url: "/pages/selFangxiang/selFangxiang"
						})
					}, 1000)
					return false;
				} else if (this.tiIndex < 10) {
					this.tiIndex = this.tiIndex + 1;
				}

			},
			// 图片加载完成
			imgload(res, index) {
				if (index == 1) {
					this.img1 = res.detail.height / 2;
				}
				if (index == 2) {
					this.img2 = res.detail.height / 2;
				}
				if (this.img1 > 0 && this.img2 > 0) {
					console.log("默认高", this.screenHeightPx)
					console.log("img1", this.img1)
					console.log("img2", this.img2)
				}
			}
		}
	}
</script>

<style>
	@import url(xycz.css);
</style>