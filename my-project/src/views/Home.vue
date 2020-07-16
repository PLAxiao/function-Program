<template>
  <div class="home">
      <p>纯函数 ：对于相同的输入永远会得到相同的输出，而且没有任何可观察的副作用。</p>
      <p> 副作用让一个纯函数变得不纯（如下两个），纯函数根据相同的输入返回相同的输出，如果函数依赖于外部的状态就无法保证</p>
      <p>相同的输出，就会带来副作用</p>
      <img src="../components/img/fun.png" alt="">

  </div>
</template>

<script>
    //不纯的函数
    let min=18;
    function checkAge1(age){
        return age>=min;
    }
    console.log(checkAge1(20))
    //普通纯函数(有硬编码)
    function checkAge2(age){
        let min=18;
        return age>=min;
    }
    console.log(checkAge2(20))
    //改变第二个例子
    function checkAge3(min,age){
        return age>=min;
    }
    console.log(checkAge3(18,20))
    console.log(checkAge3(18,24))
    console.log(checkAge3(22,24))
    //函数柯里化
    // function checkAge4(min){
    //   return function(age){
    //     return age>=min
    //   }
    // }
    //ES6
    let checkAge=min=>(age=>age>=min)

    let checkAge18=checkAge(18)
    let checkAge20=checkAge(20)
    console.log(checkAge18(20))
    console.log(checkAge20(24))


</script>
