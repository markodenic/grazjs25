<template>
  <el-row type="flex" justify="center" class="about">
      <el-col :xs="22" :sm="10">
          <h1>GrazJs #25</h1>

          <h2>"VueJS", by Marko Denić</h2>

          <h3>Presentation slides:</h3>

          <a href="https://docs.google.com/presentation/d/1Z9DEVHpRHX6mLlfRv9nzzMz2hmgCI9aLzWqV1wz7OZU/edit?usp=sharing">https://docs.google.com/presentation/d/1Z9DEVHpRHX6mLlfRv9nzzMz2hmgCI9aLzWqV1wz7OZU/edit?usp=sharing</a><br>

          <h3>Presentation code:</h3>

          <a href="https://github.com/MarkoDenic/grazjs25">https://github.com/MarkoDenic/grazjs25</a>

          <h3>Social:</h3>

          <p>
              <strong>Linkedin: </strong> <a href="https://www.linkedin.com/in/marko-denic-75b3b0a4/">https://www.linkedin.com/in/marko-denic-75b3b0a4/</a><br>
              <strong>Xing: </strong> <a href="https://www.xing.com/profile/Marko_Denic3">https://www.xing.com/profile/Marko_Denic3</a> <br>
              <strong>Twitter: </strong> <a href="https://twitter.com/denicmarko">https://twitter.com/denicmarko</a><br>
          </p>
      </el-col>
  </el-row>
</template>

<style lang="less">
    .about {
        text-align: left;
        h1, h2 {
            text-align: center;
        }
        a {
            color: #7ec5bf;
            -webkit-transition: all .2s;
            transition: all .2s;
            &:hover {
                color: lighten(#7ec5bf, 10%);
            }
        }
    }
</style>