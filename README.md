v0.15.3-cn

1. Google 文档查看器（Google Docs Viewer）
把上面两处 https://docs.google.com/viewer?url=${...}&embedded=true 改成：

js
`https://view.officeapps.live.com/op/embed.aspx?src=${encodeURIComponent(new URL(c(e),location).href)}`


把它改成 PDF.js 的 iframe 嵌入方式。国内可用的公开 CDN 推荐 BootCDN 或 jsDelivr（jsDelivr 在国内有节点，通常可用）。最精简的改法是用 PDF.js 官方 viewer 的在线地址：-6

js
`https://mozilla.github.io/pdf.js/web/viewer.html?file=${encodeURIComponent(t)}`

2. Google 地图（Google Maps）
在 _c.config（即 index.php 里的配置数组）中覆盖 map_link 为百度地图：

php
'map_link' => 'https://api.map.baidu.com/marker?location={latitude},{longtitude}&title=Location&content=Location&output=html&coord_type=wgs84&src=files.gallery',
