简简单单一个页面
要加一下公司自己的统计和分享

必须引用的有
<script src="../module/js/jquery-1.9.1.min.js"></script>
<script type="text/javascript" src="../module/js/bi.js"></script>
<script type="text/javascript" src="../module/js/action_base.js"></script>
<script src="http://res.wx.qq.com/open/js/jweixin-1.0.0.js"></script>

然后，
<!--****************************************************************-->
统计的是bi.js,这个依赖jQuery;
用法是：
    初始化的：
    //init可以不用,如有一些页面不需要改变的数据,可以预先初始化
bi.init({
    label:'问卷调查2015-05-04',
    department:'市场部', //活动部门,
    contact:'李慧美', //活动联系人,
    channel:'wx_lhm_002', //渠道,可以不填,默认自动从url上获取channel
    remark1:'有奖调查', //备注1,下同,当有一些特殊字段不满足条件时使用
    remark2:'',
    remark3:'',
    remark4:'',
    remark5:'',
});
    //统计页面访问量
bi.ready();

下面是点击按钮的：
bi.click({click:'点此进入'});

上面这句当然是要在点击事件里加的，‘点此进入’是个例子，具体看到时候的按钮的名字，那个channel是需要找统计的同事要的，一般找 wangxf，以邮件的形式。

<!--****************************************************************-->
微信分享的是action_base.js（公司自己分装的）和jweixin-1.0.0.js（微信官网必须的依赖文件，
比较懒，没有下载下来，而且官网的cdn加速比我们本地的加载的要快哦）

用法是：
var shareDate = {
    decstr:'测试描述1',
    titlestr:'测试标题1',
    imgstr:'http://phone.lkhealth.net/ydzx/business/activitiestest/fuli/images/logo.png',
    shareHref:document.location.href
};
wxShare(shareDate);

标题就是标题，描述就是描述，imgstr就是分享看到的图片,shareHref就是分享的链接，一般就是本页面地址,
imgstr一般没有人指定的话就放公司logo ，地址是http://phone.lkhealth.net/ydzx/business/activitiestest/fuli/images/logo.png
