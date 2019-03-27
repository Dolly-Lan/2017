### border-image

 border-image：border-image-source border-image-slice border-image-repeat;
 
 border-image-source: 图片路径
 
    border-image-source: url();
 
 border-image-slice： 图片裁剪
 
    border-image-slice: 50px 40px 30px 20px;  // 九宫格裁剪，代表距离左右下上四个方位50px 40px 30px 20px开始对图片进行裁剪
    
border-image-repeat：垂直方向和水平方向的重复性

  stretch（默认值：拉伸） | round（平铺） | repeat （重复）
    
    border-image-repeat： round stretch;  // 水平方向平铺，竖直方向拉伸
