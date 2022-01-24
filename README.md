<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>健康测试</title>
    <style>
        .box1{
            width: 100px;
            height: 100px;
        }
        .box{
            width: 150px;
            height: 20px;
        }
    </style>
</head>
<body>
    <center>
        <table border="1">
            <tr>
                <th>
                    身高
                    <br>
                    单位:
                    <select id="num1">
                        <option value="cm">cm</option>
                        <option value="m">m</option>
                    </select>
                </th>
                <th>
                    体重
                    <br>
                    单位:
                    <select id="num2">
                        <option value="kg">kg</option>
                        <option value="斤">斤</option>
                        <option value="g">g</option>
                    </select>
                </th>
                <th>
                    BIM
                </th>
                <th>
                    健康状况
                </th>
            </tr>
            <tr>
                <td>
                    <input class="box" type="text" id="text1" value="0"/>
                </td>
                <td>
                    <input class="box" type="text" id="text2" value="0"/>
                </td>
                <td>
                    <input class="box" type="text" id="text3" value=" "/>
                </td>
                <td>
                    <input class="box" type="text" id="text4" value=" "/>
                </td>
            </tr>
        </table>
        <input type="button" class="box1" value="计算" onclick="jisuan()"/>
    </center>
<script>
    function jisuan()
    {
        var length=parseFloat(document.getElementById("text1").value);
        var weight=parseFloat(document.getElementById("text2").value);
        var bim=1.0;
        var w1 = document.getElementById("num1");
        var k1 = w1.selectedIndex;
        var f1 = w1.options[k1].value;
        var w2 = document.getElementById("num2");
        var k2 = w2.selectedIndex;
        var f2 = w2.options[k2].value;
        if(f1==="cm")
        {
            length/=100;
        }
        if(f2==="g")
        {
            weight/=1000;
        }
        if(f2==="斤")
        {
            weight/=2;
        }
        bim=weight/(length*length);
        document.getElementById("text3").value=bim;
        if(bim<18.5)
        {
            document.getElementById("text4").value="低体重";
        }
        if(bim>=18.5&&bim<24)
        {
            document.getElementById("text4").value="正常体重";
        }
        if(bim>=24&&bim<28)
        {
            document.getElementById("text4").value="肥胖前期";
        }
        if(bim>=28)
        {
            document.getElementById("text4").value="超重";
        }
    }
</script>
</body>
</html>
