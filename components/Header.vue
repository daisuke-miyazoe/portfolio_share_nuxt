<template>
    <header>
        <p>Copyright {{ now }}</p>
        <ul>
            <li><a href="https://twitter.com/dicek_free">Twitter</a></li>
            <li><a href="mailto:hndfavodaismi@gmail.com">Mail</a></li>
            <li><a href="https://github.com/daisuke-miyazoe">Github</a></li>
        </ul>
    </header>
</template>

<script>
export default {
  data: () => {
    return {
      now: '' //取得した年数を格納
    };
  },
  created () { //年数を取得
    const d = new Date()
    this.now = d.getFullYear()
  }
}
</script>

<style scoped>
    footer {
        background-color: #000;
        color: #fff;
        padding: 0 20px;
        margin-top: 160px;
    }
    ul > li {
        display: inline-block;
        margin-right: 2em;
    }
    ul a {
        color: #fff;
        text-decoration: none;
    }
    @media (min-width: 768px) {
        footer {
            padding: 0;
            height: 50px;
            display: grid;
            grid-template-columns: 1fr 700px 1fr;
            grid-template-rows: 1fr;
        }
        footer > * {
            grid-column: 2;
            grid-row: 1;
        }
        p {
            justify-self: start;
            align-self: center;
        }
        ul {
            justify-self: end;
            align-self: center;
        }
    }
    @media (min-width: 1024px) {
        footer {
            grid-template-columns: 1fr 980px 1fr;
        }
    }
</style>
