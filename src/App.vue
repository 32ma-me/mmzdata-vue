<script setup>
document.title="もみじの音源保管庫"
import gridGeneral from "./components/gridGeneral.vue"
import gridAlbums from "./components/gridAlbums.vue"
const year=new Date().getFullYear()
</script>

<template>
  <header>
        <h1>もみじの音源保管庫</h1>
        <p>今までに作った楽曲のデータをダウンロードできます。</p>
        <h3>Notice</h3>
        <p style="font-size:0.8em;margin:0.5em 0;">
            私の作った楽曲はご自由にご利用下さい。<br>
            ダウンロード、転載、リミックス等どんな目的でご利用の方でも連絡は不要です。<br>
            クレジット表記は無くても大丈夫です。書いていただけると嬉しいな、ぐらいなのです。
        </p>
        <p style="margin-top:0;">ですが、<span style="font-weight:600;">私の楽曲を用いて特定の方を貶したりする行為は絶対許しません</span>。</p>
  </header>
  <main>
    <h2>Songs</h2>
    <div class="grid">
      <gridGeneral :link="'http://mmzdata.starfree.jp/monogatari.mp3'" :text="'物語'" :hover="'Download'"/>
      <gridGeneral :link="'http://mmzdata.starfree.jp/monogatari_gumi.mp3'" :text="'物語(Another)'" :hover="'Download'"/>
      <gridGeneral :link="'http://mmzdata.starfree.jp/monogatari_karaoke.mp3'" :text="'物語(Instrumental)'" :hover="'Download'"/>
      <gridGeneral :link="'http://mmzdata.starfree.jp/2K.mp3'" :text="'2K'" :hover="'Download'" :color="'yellow'" :newline="true"/>
      <gridGeneral :link="'http://mmzdata.starfree.jp/2K_karaoke.mp3'" :text="'2K(Instrumental)'" :hover="'Download'" :color="'yellow'"/>
      <gridGeneral :hover="'Coming Soon...'" :newline="true"/>
    </div>
    <h2>Albums(工事中)</h2>
    <div class="albumgrid">
      <gridAlbums :link="'https://fanlink.to/ik1mgbs'" :text="'Ⅰ期'" :image="'/img/noimage.webp'"/>
      <gridAlbums :link="'https://fanlink.to/ik2mgbs'" :text="'Ⅱ期'" :image="'/img/noimage.webp'"/>
      <gridAlbums :link="'https://fanlink.to/ik3mgbs'" :text="'Ⅲ期'" :image="'/img/noimage.webp'"/>
      <gridAlbums :text="'Ⅳ期'" :image="'/img/noimage.webp'"/>
      <gridAlbums :image="'/img/noimage.webp'"/>
    </div>
    <h2>Links</h2>
    <div class="grid">
      <gridGeneral :link="'https://twitter.com/momizi_SBGM'" :text="'Twitter'" :hover="'@momizi_SBGM'" :color="'blue'"/>
      <gridGeneral :link="'https://youtube.com/@subegumi'" :text="'YouTube(模倣)'" :hover="'@subegumi'" :color="'red'"/>
      <gridGeneral :link="'https://youtube.com/@onjo0'" :text="'YouTube(その他)'" :hover="'@onjo0'" :color="'red'"/>
      <gridGeneral :link="'https://soundcloud.com/sbgm_sc'" :text="'SoundCloud'" :hover="'@sbgm_sc'" :color="'orange'"/>
      <gridGeneral :link="'https://misskey.io/momizi'" :text="'Misskey'" :hover="'@momizi'" :color="'misskey'"/>
    </div>
  </main>
  <footer>
    <p>
      &#169;2020-{{year}} 椛<br>
      Website Designed by <a href="https://twitter.com/_32ame">実つまめ @_32ame</a>
    </p>
  </footer>
</template>

<style scoped>
div.albumgrid{
    transition:.5s;
    justify-content:center;
    margin:auto;
    display:grid;
    grid-template-columns:repeat(auto-fill,300px);
    grid-template-rows:repeat(auto-fill,300px);
    grid-gap:5px;
}
div.grid{
    justify-content:center;
    margin:auto;
    display:grid;
    grid-template-columns:repeat(auto-fill,300px);
    grid-template-rows:repeat(auto-fill,100px);
    grid-gap:5px;
}
a,a:visited{
    transition:.5s;
    color:#171717;
    text-decoration:none;
}
a:not(.griditem):hover{
    color:#909090;
}
footer{
    text-align:center;font-size:0.6em;margin-top:30px;margin-bottom:-20px;
}
</style>