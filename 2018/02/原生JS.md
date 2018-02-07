### removeChild(thisNode)

[参考资料](http://www.itxueyuan.org/view/6356.html)

此方法只提供删除子节点，可以通过parentNode获取父节点再删除当前节点

    let thisNode = document.getElementById("dashboard")
    thisNode.parentNode.removeChild(thisNode)
