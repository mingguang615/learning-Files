# js计算时间范围的方法

	```
    	function time_range(beginTime, endTime) {
        let strb = beginTime.split(":");
        if (strb.length != 2) {
            return false;
        }

        let stre = endTime.split(":");
        if (stre.length != 2) {
            return false;
        }

        let b = new Date();
        let e = new Date();
        let n = new Date();

        b.setHours(strb[0]);
        b.setMinutes(strb[1]);
        e.setHours(stre[0]);
        e.setMinutes(stre[1]);

        if (n.getTime() - b.getTime() > 0 && n.getTime() - e.getTime() < 0) {
            return true;
        } else {
            alert("当前时间是：" + n.getHours() + ":" + n.getMinutes() + "，不在该时间范围内！");
            return false;
        }
    }
    let result = time_range("08:10", "08:50");
    ```