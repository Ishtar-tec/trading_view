<template>
 <div>
<div id="tv_chart_container"></div>
 </div>
</template>

<script>
function getParameterByName(name) {
        name = name.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");
        var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
            results = regex.exec(location.search);
        return results === null ? "" : decodeURIComponent(results[1].replace(/\+/g, " "));
    }

    function initOnReady() {
        var widget = new TradingView.widget({
            fullscreen: true,
            symbol: 'AAPL',
            interval: '1D',
            container: "tv_chart_container",
            //	BEWARE: no trailing slash is expected in feed URL
            datafeed: new Datafeeds.UDFCompatibleDatafeed("https://demo-feed-data.tradingview.com"),//数据
            library_path: "charting_library/",
            locale: getParameterByName('lang') || "en",

            disabled_features: ["use_localstorage_for_settings"],
            preset: "mobile",
            overrides: {
                "paneProperties.background": "#212121",
                "paneProperties.vertGridProperties.color": "#454545",
                "paneProperties.horzGridProperties.color": "#454545",
                "scalesProperties.textColor" : "#AAA"
            }
        });
    };

    window.addEventListener('DOMContentLoaded', initOnReady, false);
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {

     }
   },
   methods: {
       
   },
   mounted() {

   },
 }
</script>

<style scoped lang='less'>

</style>