# csdn文件下载

优惠劵：
      - 12-13号90元；12-14号90元；12-18号50元；
首次认证学生信息当天享7折，后续8折。工作认证8折；
年卡里面才能使用50元优惠券；
上传一张资料后：
2年vip：488.00原价。390.40元 已优惠97.60元！
1年vip： 298.00原价。238.40元 已优惠59.60元！
优惠不会叠加；
充值赠送年卡。但多充值几百元，似乎用不上；以后恐怕也没有优惠了。
微信小程序里连续签到7天，有100元优惠券。比学生折扣更低？198/400=0.495，似乎比2年卡8折扣更贵。
VIP会员·优惠劵：每天30。续费大概是8折 -30元；= 298 * 0.8 - 30 = 208 = 90元优惠券；
连续签到拿余额和优惠券。如果可以叠加，大概就是免年卡。
连续签到7天 = 108元优惠；
充值800 = 800 / 200 + 1 = 5 * 400 = 2000 ；  800/2000=0.4元;
假如7折： 基本一样，只有首次7折。如果是
06-17活动，加赠618次下载；100元抵扣券；只有2022年；
非vip连续签到一次，大概0.3元/次；
vip签到一次，平均每次1.1元；连续签到200次，就等同于免费一年。
最大化：充值800 + 学生证 * 488 七折；连续签到7天90元优惠券和1年会员的7折扣相同；
2年会员*
最可靠简单的方式：
- 1、充值800，默认8折 + 叠加30元红包；
- 2、签到7天；80~90 优惠券；8折+优惠券；

问题：每日20个资源。如果每天下次次数超过20次，一个账号不够用。400次/20=200天；
可能冻结或封号；
- csdn会员，连续签到7天，必有100元优惠券=10+60+30的分类红包；
- 新人专享券，直降60元。
- 访问网页有新人专享礼包；


是否可以注册多个账号，签到领红包，汇总余额。
自定义域名  https://mp.csdn.net/mp_blog/creator-plan/config-domain?spm=1000.2116.3001.6283
登录日志；https://i.csdn.net/#/user-center/account/log



- 寻找无积分下载资料，https://download.csdn.net/download/qq_54192572/87885020
- 必须登录后才能调用接口；

## csdn关键协议
### 获取下载链接
- 在已登录的页面中请求成功
- 直接在未登录的页面中发送带cookdie的fetch请求失败。
- 在新页面中直接调用协议，运行正常。无需点击立刻下载。重要的是登录状态。
- 只需要在不会cors的download.csdn.net中就可以正常触发下载协议；

fetch("https://download.csdn.net/api/source/detail/v1/download", {
  "headers": {
    "content-type": "application/json",
    "sec-ch-ua": "\"Not_A Brand\";v=\"8\", \"Chromium\";v=\"120\", \"Google Chrome\";v=\"120\"",
    "Referer": "https://download.csdn.net/download/mapleandleaf/4040027?spm=1001.2014.3001.5501",
  },
  "body": "{\"sourceId\":4040027}",
  "method": "POST",
});

失败：{    "code": 400,    "message": "请登录后操作"}
成功：{    "code": 200,    "message": "ok",
    "data": "https://dl-download.csdn.net/down10/20120201/a8b7979d0e78a2b680abadd470d785d5.rar?Expires=1702907217&OSSAccessKeyId=STS.NUhHMjhDKk1bjAmLafLThcssc&Signature=Fd2PNBgilUUyLEQtQVZeE4LDHEQ%3D&response-content-disposition=attachment%3Bfilename%3D%22%25E7%25A0%25B4%25E8%25A7%25A3%25E6%2596%2587%25E4%25BB%25B6.rar%22&Date=1702907217&security-token=CAISgwJ1q6Ft5B2yfSjIr5bdA%2FfehZtq3POJaGfcqGEzQNtEjLbYgTz2IHxFf3FoCOEYv%2Fk1nWlU6%2FoTlqF%2FTIBDQUvNYZPHHmzUXlrzDbDasumZsJYw6vT8a1fxZjf%2F2MjNGaCbKPrWZvaqbX3diyZ32sGUXD6%2BXlujQ%2BDr6Zl8dYY4UxX6D1tBH8wEAgp5tI1gQhm3D%2Fu2NQPwiWf9FVdhvhEG6Vly8qOi2MaRmHG85R%2FYsrZJ%2FtuvecD%2FMJI3Z8kvC4uPsbYoJvab4kl58ANX8ap6tqtA9Arcs8uVa1sruEnXaLKMo4wxfVIjP%2FFmRvIVtprnieY9tuiWkJ%2Fs25qImF%2BBkY61GoABgGeQcZE7roTJrsee%2BMTCJJ6rg9dBDqD7FPbCoRLQhEr9XccM97NKhGecnJYaof1uW4%2BPAqTEClPIJ8dx97vTKGWIgRczxA0%2BE%2FtQl4IV%2BiBnB%2FdmwiSYVzmmznzqDH6MSa1EzF5IH7AaZz9C4eukwsXK3GqyTpJv5nkCn16M5zYgAA%3D%3D"
}
Expires  连接有效期1分钟。不超过5分钟。

decode后的内容
https://dl-download.csdn.net/down11/20230609/c326d64512ae5be085190823c40c011b.msi?Expires=1703149405&OSSAccessKeyId=STS.NTgwLBUaGWhmP2JawSBiFb2QV&Signature=wc56vadtvVjFVo4ur+kQ6bzQgsQ=&response-content-disposition=attachment;filename="charles-proxy-4.6.4-win64.msi"&Date=1703149405&security-token=CAISgwJ1q6Ft5B2yfSjIr5fSPPb2uL5m4KqGUhT7hXcGTuZqjff6tDz2IHxFf3FoCOEYv/k1nWlU6/oTlqF/TIBDQUvNYZOBFjLhUVrzDbDasumZsJYw6vT8a1fxZjf/2MjNGaCbKPrWZvaqbX3diyZ32sGUXD6+XlujQ+Dr6Zl8dYY4UxX6D1tBH8wEAgp5tI1gQhm3D/u2NQPwiWf9FVdhvhEG6Vly8qOi2MaRmHG85R/YsrZJ/tuvecD/MJI3Z8kvC4uPsbYoJvab4kl58ANX8ap6tqtA9Arcs8uVa1sruEnXaLKMo4wxfVIjP/FmRvIVtprnieY9tuiWkJ/s25qImF+BkY61GoABr0MKyMMjqURws2J1FG6RCKk/J8GeQrYkD5MSLveKZWrY5NN/mjTPWesUm8x4gq8qOjxX+nXUeqCHgGwQgkgZnSUgUCMcDAhtqzwEJjSQZMV6rIti61QLK2EuOzzmnw/LyKaF3PznLmjdSjltL/Fyd14ZpB8T0ToQCBCwOv+w/gcgAA==



测试无积分文件：
fetch("https://download.csdn.net/api/source/detail/v1/download", {
  "headers": {
    "content-type": "application/json",
    "sec-ch-ua": "\"Not_A Brand\";v=\"8\", \"Chromium\";v=\"120\", \"Google Chrome\";v=\"120\"",
    "Referer": "https://download.csdn.net/download/qq_54192572/87885020",
  },
  "body": "{\"sourceId\":87885020}",
  "method": "POST",
});

可以直接调用协议，只是发送协议，网页中也有发出了事件协议。大概是反爬之类。
https://wkbrs1.tingyun.com/action?url=https%3A%2F%2Fdownload.csdn.net%2Fdownload%2Fqq_54192572%2F87885020&pvid=c23738ca34734c4db92fa819fc2f0fe8&ref=https%3A%2F%2Fdownload.csdn.net%2Fdownload%2Fqq_54192572%2F87885020&referrer=https%3A%2F%2Fpassport.csdn.net%2Flogin%3Fcode%3Dapplets&v=3.3.1-saas.2&av=3.3.1-saas.2&did=10_18228179250-1690274162415-988826&uid=shudaotu&sid=4d228538f9d749dc88e49b7412eba67a&__s=1702984891388&id=oxCR3HG3rnM&key=jcyC7WVM7Ho&token=8399f6662a2747fc872cacd390930886&sh=1080&sw=1920&ps=0&__r=1702985747210

需要拦截协议：https://dl-download.csdn.net

### 获取用户账号信息
fetch("https://g-api.csdn.net/community/toolbar-api/v1/get-user-info", {
  "headers": {
    "content-type": "application/x-www-form-urlencoded; charset=utf-8",
    "sec-ch-ua": "\"Chromium\";v=\"122\", \"Not(A:Brand\";v=\"24\", \"Google Chrome\";v=\"122\"",
  },  
  "method": "GET",
  "credentials": "include"
});
{
    "code": 200,
    "msg": "success",
    "data": {
        "nickName": "书导图",
        "avatar": "https://profile-avatar.csdnimg.cn/default.jpg!1",
        "fansCount": 0,
        "likeCount": 0,
        "vip": 2,
        "followCount": 0
    }
}


await page.click("#downloadBtn");

await page.waitForFunction(() => {
    const buttonText = document.querySelector(".el-dialog__wrapper div.el-dialog__footer button").innerText;
    return buttonText == '立即下载' || buttonText == "VIP专享下载" ;
});

await page.click(".el-dialog__wrapper div.el-dialog__footer button"); // 点击下载
await sleep(1000);

page.evaluate(() => {
    // 查看优惠券
    const dialogs = document.querySelectorAll(".coupon-dialog");

    dialogs.forEach((dialog) => {
        if (dialog.innerText) {
            dialog.querySelector(".el-dialog__headerbtn").click();
        }
    });
})





