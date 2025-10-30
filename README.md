# python-argo-modal

## 必要的变量——在 action 仓库机密中设置

### Modal的变量

- **MODAL_TOKEN_ID** = modal api token 的 ID         // 必须
- **MODAL_TOKEN_SECRET** = modal api token 的秘钥    // 必须
- **MODAL_USER_NAME** = modal 账号的用户名            // 必须
- **MODAL_APP_NAME** = modal 项目名                  // 不填则使用默认

### 节点所需变量

- **UUID** = 82ab6c19-b0c4-4d2a-93d1-af0687edfe76    // 不填则使用内置默认uuid
- **ARGO_DOMAIN** = argo 域名                        // 必须，model必须使用固定隧道，临时隧道不通
- **ARGO_AUTH** = eyxxxxxxxxxxxxxxxxxxxxxxxxxxx     // 必须，model必须使用固定隧道，临时隧道不通
- **NEZHA_SERVER** = 哪吒 agent 域名，v1为 域名:端口  // 可选
- **NEZHA_KEY** = 哪吒 agent 的 key                  // 可选
- **NEZHA_PORT** = 哪吒 agent 的 端口，仅v0需要       // 可选
- **CFIP** = cf.090227.xyz                          // 优选域名或IP，可选，不填则使用默认
- **CFPORT** = 443                                  // 优选域名或优选IP的端口，可选，不填则使用默认
- **NAME** = Modal                                  // 节点名称前缀，可选，不填则使用默认
- **CFPORT** = 443                                  // 优选域名或优选IP的端口，可选，不填则使用默认
- **BOT_TOKEN** = TG 机器人 Token                   // 可选
- **CHAT_ID** = TG 机器人或频道 ID                   // 可选

oad 区域名	Specific 具体区域 ID	英文描述 / English Description	中文说明
us-east	us-east-1	AWS 弗吉尼亚州	亚马逊美国弗吉尼亚州（东部）
us-east-2	AWS 俄亥俄州	亚马逊美国俄亥俄州
us-east1	GCP 南卡罗来纳州	谷歌云美国南卡罗来纳州
us-east4	GCP 弗吉尼亚州	谷歌云美国弗吉尼亚州
us-east5	俄亥俄州 GCP	谷歌云美国俄亥俄州
us-ashburn-1	OCI 弗吉尼亚州	甲骨文云美国弗吉尼亚州
us-central	us-central1	GCP 爱荷华州	谷歌云美国艾奥瓦州
us-chicago-1	OCI 芝加哥	甲骨文云美国芝加哥
us-phoenix-1	OCI 凤凰城	甲骨文云美国凤凰城
us-west	us-west-1	AWS 加利福尼亚	亚马逊美国加州（西部）
us-west-2	AWS 俄勒冈州	亚马逊美国俄勒冈州
us-west1	GCP 俄勒冈州	谷歌云美国俄勒冈州
us-west3	GCP 犹他州	谷歌云美国犹他州
us-west4	GCP 内华达州	谷歌云美国内华达州
us-sanjose-1	OCI 圣何塞	甲骨文云美国圣何塞
eu-west	eu-central-1	AWS 法兰克福	亚马逊德国法兰克福
eu-west-1	AWS 爱尔兰	亚马逊爱尔兰
eu-west-3	AWS 巴黎	亚马逊法国巴黎
europe-west1	GCP 比利时	谷歌云比利时
europe-west3	GCP 法兰克福	谷歌云德国法兰克福
europe-west4	GCP 荷兰	谷歌云荷兰
eu-frankfurt-1	OCI 法兰克福	甲骨文云德国法兰克福
eu-paris-1	OCI 巴黎	甲骨文云法国巴黎
eu-north	eu-north-1	AWS 斯德哥尔摩	亚马逊瑞典斯德哥尔摩
ap-northeast	asia-northeast3	GCP 首尔	谷歌云韩国首尔
asia-northeast1	GCP东京	谷歌云日本东京
ap-northeast-1	AWS 东京	亚马逊日本东京
ap-northeast-3	AWS 大阪	亚马逊日本大阪
ap-southeast	asia-southeast1	GCP 新加坡	谷歌云新加坡
ap-southeast-3	AWS 雅加达	亚马逊印度尼西亚雅加达
ap-south	ap-south-1	AWS 孟买	亚马逊印度孟买
ca	ca-central-1	AWS 蒙特利尔	亚马逊加拿大蒙特利尔
ca-toronto-1	OCI 多伦多	甲骨文云加拿大多伦多
uk	uk-london-1	OCI 伦敦	甲骨文云英国伦敦
europe-west2	GCP 伦敦	谷歌云英国伦敦
eu-west-2	AWS 伦敦	亚马逊英国伦敦
jp	ap-northeast-1	AWS 东京	亚马逊日本东京
ap-northeast-3	AWS 大阪	亚马逊日本大阪
asia-northeast1	GCP东京	谷歌云日本东京
me	me-west1	特拉维夫 GCP	谷歌云以色列特拉维夫
sa	sa-east-1	AWS 圣保罗	亚马逊巴西圣保罗
## 保活

项目24小时后会自动关闭，关闭的项目无法再唤醒，保活逻辑采用重部署方式

### 保活方式1：action 定时任务

每天凌晨2点重部署，删除工作流中定时触发器的 `#` 号注释，即可启用

### 保活方式2：uptime+webhook 启动 action

具体教程：<https://blog.811520.xyz/post/2025/09/250916-uptime-action/>
