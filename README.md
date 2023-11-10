# F2E

[F2E 活動網址](https://2023.thef2e.com/)

[使用設計稿](https://www.figma.com/file/HA37QuZPLzzS7NaDow2QLO/%E5%85%AD%E8%A7%92?node-id=46%3A10&mode=dev)

[website](https://narrowd4c.github.io/F2E-xru66/)

待解決
- [X] 政策議題 swiper 重構   
   ##### 問題: 當滑動方向改為垂直時，slide-wrapper 高度會無限擴張，先以 `max-height:557px;` 代替。     
   ##### 解決方式：使用 `autoHeight:true 參數`, 並在 swiper-slide 添加 `height:auto;`   
   參考: https://github.com/nolimits4web/swiper/issues/4599  
   參考: https://swiperjs.com/swiper-api#param-autoHeight
