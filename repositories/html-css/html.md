## SEO
SEO(Search Engine Optimization)：搜索引擎优化
* 语义化标签
* TDK：title、description、keywords，seo页面中的页面描述与关键词设置

## async和defer
- 遇到 async 时，浏览器在异步下载完这个脚本后，中断页面渲染，优先执行这个脚本后再继续渲染。
- 遇到 defer 时，浏览器会先将整个页面正常渲染完成（DOM结构完全生成以后，以及同步的 js 脚本）执行完后才会执行
- defer 是渲染完再执行，async 是下载完就执行。
- 如果页面有多个 defer 脚本，会按照它们出现的文件顺序加载，而多个 async 脚本是不能保证加载顺序的（与加载完成顺序有关）。