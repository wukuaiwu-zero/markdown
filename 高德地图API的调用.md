### 引入高德地图
#### 首先在开发者控制台创建新应用，域名白名单在开发时为空，新增安全密钥搭配key使用
#### 通过高德官方提供的插件引入 JSAPI Loader
`npm i @amap/amap-jsapi-loader --save`

	import AMapLoader from '@amap/amap-jsapi-loader';

	AMapLoader.load({
		"key": "",              // 申请好的Web端开发者Key，首次调用 load 时必填
		"version": "2.0",   // 指定要加载的 JSAPI 的版本，缺省时默认为 1.4.15
		"plugins": [],           // 需要使用的的插件列表，如比例尺'AMap.Scale'等
	}).then((AMap)=>{
		map = new AMap.Map('container');
	}).catch(e => {
		console.log(e);
	})
### JSAPI key和安全密钥的使用

	<script type="text/javascript">
        window._AMapSecurityConfig = {
            securityJsCode:'您申请的安全密钥',
        }
	</script>
	<script type="text/javascript" src="https://webapi.amap.com/maps?v=2.0&key=您申请的key值"></script> 

引入地图 JSAPI 脚本之前增加设置 JSAPI 安全密钥的脚本标签，并将您的安全密钥「您申请的安全密钥」替换为您的安全密钥    
（注意这个设置必须是在  JSAPI 的脚本加载之前进行设置，否则设置无效。）