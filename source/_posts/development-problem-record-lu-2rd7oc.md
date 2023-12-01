<p><img src="assets/unsplash-THB1yHtmT2E-20231201100227-bn11lxi.jpg" alt="image" /></p>
<h1>开发问题记录📝</h1>
<h2>vant组件开发相关问题</h2>
<ul>
<li>
<p>vant开发的组件库初次渲染没问题,只要跳转至其他页面再进来设置的label-align属性就会丢失不生效</p>
<ol>
<li>
<p>原因: 进入其他页面加载了主项目的vant库的css优先级层级高,然后就把组件本身的样式覆盖了,</p>
<ol>
<li>​​<img src="assets/image-20231201094126-xywjoqc.png" alt="image" />​​</li>
</ol>
</li>
<li>
<p>解决思路: 使用渗透把主项目的样式给重写覆盖</p>
<ol>
<li>​<img src="assets/image-20231201094150-52yelat.png" alt="image" />​</li>
<li>​<img src="assets/image-20231201094242-xagu8lw.png" alt="image" />​​</li>
</ol>
</li>
</ol>
</li>
</ul>
<p>‍</p>
