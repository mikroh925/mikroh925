if requirements.txt=README.md, else var s,d=e("./Constants.js"),c=e("./OMIDConstants")
!function(e){if("object"==typeof exports&&"undefined"!=typeof module)module.exports=e();else if("function"==typeof define&&define.amd)define([],e);else{("undefined"!=typeof window?window:"undefined"!=typeof global?global:"undefined"!=typeof self?self:this).Eventics=e()}}(function(){return function a(o,s,d){function c(t,e){if(!s[t]){if(!o[t]){var n="function"==typeof require&&require;if(!e&&n)return n(t,!0);if(l)return l(t,!0);var i=new Error("Cannot find module '"+t+"'");throw i.code="MODULE_NOT_FOUND",i}var r=s[t]={exports:{}};o[t][0].call(r.exports,function(e){return c(o[t][1][e]||e)},r,r.exports,a,o,s,d)}return s[t].exports}for(var l="function"==typeof require&&require,e=0;e=minimumAdsForExtraOffersInventory)}function _test(){var re=/(\(\))$/,args=[].slice.call(arguments),name=args.shift(),is_method=re.test(name),target;return name=name.replace(re,""),target=eval(name),is_method?target.apply(this,args):target}return{isSupported:_isSupported,fetchExtraOffersInventory:_fetchExtraOffersInventory,test:_test}}module.exports=ExtraOffers},{}],17:[function(e,t,n){t.exports=function(i,r,a,o,n){return{isFeatureSupportedInNativeSDK:function(e){var t=!1;return e&&n&&n.nativeFeatures&&(t=Array.isArray(n.nativeFeatures)&&-1",{class:i,src:e.url}).data("id",n).data("close",!0).appendTo("body")}(e,i.preload)}function r(e){var t=l(".loaderOW");t.addClass("loaderOWFadeOut"),setTimeout(function(){h("hideLoader - enter timeOut"),l(".loaderOW").addClass("hidden"),t[0].offsetWidth=t[0].offsetWidth},600),l("#ssaLoaderWrap").addClass("hidden")}function v(e,t,n,i){r(),n(!1),d.set(t),e.removeClass("hidden").attr("id","displayedFrame"),i()}function m(e,t){e===o.OW?l(".loaderOW").removeClass("loaderOWFadeOut hidden"):l("#ssaLoaderWrap").removeClass("hidden")}function n(e,t,n){t&&(n=n||parent).postMessage(e,t.replace(/([^:]+:\/\/[^\/]+).*/,"$1"))}function h(e){a.log(c+e)}return{createAndLoadAdFrame:p,updateAdUnitUrl:function(e,t,n,i){var r;f(e,t,n,i),(r=g(e))?(h("updated iframe url for product "+n.productType),r[0].src=e.url):i.forceCreation?(h("cannot find iframe to update, creating new one"),p(e,t,n,i)):a.log(c+"cannot find iframe to update url")},displayAdView:function(e,t,n,i){var r=g(e);r.data("loaded")?(h("display frame"),l.when(i(e,!1)).done(function(){v(r,e,t,n)})):(h("display frame with loader"),d.set(e),l.when(i(e,!0)).done(function(){!function(e,t,n,i){if(e.data("loaded"))return v(e,t,n,i);n(!0),a.log(c+"display with loader, frame "+e.data("id")),t&&t.productType&&(m(t.productType),e.attr("id","displayedFrame"))}(r,e,t,n)}))},handleScreenVisible:function(e,t){e&&m(t.productType);var n=s.getDisplayedAdFrame();n&&(h("ad unit open error"),n.addClass("hidden").attr("id",""))},unloadAdView:function(n){var i=n.adViewId;h("unloading ad from frame | id:"+i+" pt: "+n.productType),l.each(l(s.getAdUnitClassObj(n).selector),function(e,t){return l(t).data("id")!==i||(n.engaged&&t.removeAttribute("id"),n.productType===o.OW?setTimeout(function(){t&&t.parentNode&&t.parentNode.removeChild(t)},0):t&&t.parentNode&&t.parentNode.removeChild(t),!1)})},displayLoader:m,hideLoader:r,hideView:s.hideFrame,displayView:s.displayFrame,isContainerLoaded:function(e){var t=!!g(e);return h("isContainerLoaded: "+t),t},onAdUnitLoaded:function(e,t,n){var i=g(e);if(i)if(i.data("loaded"))h("already received the loaded event for frame");else{i.data("loaded",!0);var r=s.isFrameDisplayed(i);h("ad loaded: "+a.AdUtils.getAdId(e)+" | "+r?"frame Displayed: true":"frame Displayed: false|"+s.getAdUnitClassObj(e).selector),r&&v(i,e,t,n)}},getAdViewByAd:g,sendMessageToDisplayedAdView:function(e){var t=s.getDisplayedAdFrame();t&&n(JSON.stringify(e),"*",t[0].contentWindow)},sendMessageToAllAdViews:function(e){l.each(l(".ssaAdUnit"),function(){n(JSON.stringify(e),"*",this.contentWindow)})},getDisplayedAdView:s.getDisplayedAdFrame,isViewDisplayed:s.isFrameDisplayed,getContainerID:function(){return"1"}}}},{}],27:[function(e,t,n){t.exports=function(r){var e=[];function a(t){return function(e){return e.demandSourceName===s(t)&&e.productType===t.productType}}function n(e){for(var t=0,n=0;ni&&delete r[t.shift()]}function u(e,t){if(Array.isArray(e)&&0!==e.length){var n=void 0!==t?t:D();void 0===r[n]&&(n=D());for(var i=0;ie||t.bottom>e||t.right>e||t.left>e}}(),{hasNotch:a,onEngageEnd:function(){i!==n.deviceOs.android&&a()},onSetConfig:function(e){return i!==n.deviceOs.android&&a()&&(t=e).settings&&t.settings.standaloneView;var t},className:"NotchService"}}},{}],39:[function(e,t,n){t.exports={omidNativeFunction:"omidAPI",activateSuccessKey:"omidActivateSuccess",activateFailKey:"omidActivateFail",startSessionSuccessKey:"omidStartSessionSuccess",startSessionFailKey:"omidStartSessionFail",finishSessionSuccessKey:"omidFinishSessionSuccess",finishSessionFailKey:"omidFinishSessionFail",impressionOccurredSuccessKey:"omidimpressionOccurredSuccess",impressionOccurredFailKey:"omidimpressionOccurredFail",omidFailedToLoadBundleMessage:"Failed to load OMID JS Bundle",omidFailedToDownloadMessage:"Failed to download and cache OMID JS Bundle",omidFailureInStartSession:"Failure in starting session",omidFailureInFinishSession:"Failure in finishing session",omidFailureInImpressionOccurred:"Failure in impression occurred",omidBundleFilePrefix:"omid-daemon-",omidBundleFileType:".js",stopOMIDServiceDelay:1e3,omidPartnerName:"Ironsrc",omidPartnerVersion:"6",omidServiceName:"omid",omidBundleDefaultVersionKey:"default",omidVersionMapping:{"1.2.22-Ironsrc":"1.0.0","1.3.12-Ironsrc":"1.3.12",default:"1.0.0"},omidVersionRequiresWebviewPerAd:{"1.2.22-Ironsrc":!1,"1.3.12-Ironsrc":!0,default:!1},omidVersionIsControllerDownloadOMSDK:{"1.2.22-Ironsrc":!0,"1.3.12-Ironsrc":!1,default:!1}}},{}],40:[function(e,t,n){t.exports=function(r,a,o){var s,d=e("./Constants.js"),c=e("./OMIDConstants"),l=!1,u=!1,f="",g=d.omidPartnerVersion,p="",t=null,v=null,m=null,h=null,b=null;function n(){if(!l){if(v&&"pending"===v.state())return v;v=new o.Deferred,a.log("OMIDService - activate",a.LogLevels.verbose);var n=r.PubSub.subscribe(d.CB+"."+c.activateSuccessKey,function(e){var t;f=e&&e.omidVersion?e.omidVersion:"",g=e&&e.omidPartnerVersion?e.omidPartnerVersion:d.omidPartnerVersion,l=!0,r.PubSub.clearHandlers([n,i]),r.PubSub.subscribe("SDKController.OMIDStartSession",function(e){S(e)}),r.PubSub.subscribe("SDKController.OMIDFinishSession",function(){y()}),r.PubSub.subscribe("SDKController.OMIDImpressionOccurred",function(e){!function(e){if(!A()||!l||!u){var t=c.omidFailureInImpressionOccurred+" didLoadOMSDKService "+A()+" omidServiceActivated "+l+" isSessionStarted "+u;return r.PubSub.publish("SDKController.onOmidServiceFailure",[t])}if(!b||"pending"!==b.state()){b=new o.Deferred;var n=r.PubSub.subscribe(d.CB+"."+c.impressionOccurredSuccessKey,function(e){r.PubSub.clearHandlers([n,i]),a.log(c.omidNativeFunction+" Impression Occurred success: "+JSON.stringify(e),a.LogLevels.verbose),b.resolve()}),i=r.PubSub.subscribe(d.CB+"."+c.impressionOccurredFailKey,function(e){r.PubSub.clearHandlers([n,i]);var t=e&&e.errMsg?e.errMsg:"";a.log(c.omidNativeFunction+" Impression Occurred fail: "+JSON.stringify(e),a.LogLevels.verbose),r.PubSub.publish("SDKController.onOmidServiceFailure",[t]),b.reject()});a.callSDKFunction(c.omidNativeFunction,{omidFunction:"impressionOccurred",omidParams:e},c.impressionOccurredSuccessKey,c.impressionOccurredFailKey),b.promise()}}(e)}),t=C(f),p=s.getExternalLibrariesUrl()+c.omidServiceName+"/"+t+"/"+c.omidServiceName+c.omidBundleFileType,a.log(c.omidNativeFunction+" activate success: "+JSON.stringify(e),a.LogLevels.verbose),v.resolve()}),i=r.PubSub.subscribe(d.CB+"."+c.activateFailKey,function(e){r.PubSub.clearHandlers([n,i]);var t=e&&e.errMsg?e.errMsg:"";a.log(c.omidNativeFunction+" activate session fail: "+JSON.stringify(e),a.LogLevels.verbose),r.PubSub.publish("SDKController.onOmidServiceFailure",[t]),v.reject()});return a.callSDKFunction(c.omidNativeFunction,{omidFunction:"activate",omidParams:{}},c.activateSuccessKey,c.activateFailKey),v.promise()}a.log("OMIDService - activate OMID is already initialized",a.LogLevels.verbose)}function S(e){if(A()&&l){if(m&&"pending"===m.state())return m;m=new o.Deferred,a.log("OMIDService - startSession",a.LogLevel


workflow will upload a Python Package using Twine when a release is created
# For more information see: https://help.github.com/en/actions/language-and-framework-guides/using-python-with-github-actions#publishing-to-package-registries

name: Upload Python Package

on:
  release:
    types: [created]

jobs:
  deploy:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: '3.x'
    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install setuptools wheel twine
    - name: Build and publish
      env:
        TWINE_USERNAME: ${{ secrets.PYPI_USERNAME }}
        TWINE_PASSWORD: ${{ secrets.PYPI_PASSWORD }}
      run: |
        python setup.py sdist bdist_wheel
        twine upload dist/*
Swap:%16llu%12llu%12llu
internalPath=mnt/media_rw/3160-14EE/,.shstrtab.interp.note.android.ident.note.gnu.build-id.dynsym.dynstr.gnu.hash.gnu.version.gnu.version_r.rel.dyn.rel.plt.text.ARM.exidx.rodata.ARM.extab.data.rel.ro.local.preinit_array.init_array.fini_array.dynamic.got.data.bss.comment.note.gnu.gold-version.ARM.atributes[build | s% [b]],Alfa-m.ONE .shstrtab.interp.note.android.ident.note.gnu.build-id.dynsym.dynstr.gnu.hash.gnu.version.gnu.version_r.rel.dyn.rel.plt.text.ARM.exidx.rodata.ARM.extab.data.rel.ro.local.preinit_array.init_array.fini_array.dynamic.got.data.bss.comment.note.gnu.gold-version.ARM.atributes[build | s% [b]],Alfa-m.ONE


cid:framebind "b" "verticalline";Swap:%16llu%12llu%12llu {Unknown command '%s,b'{Toybox command list 
{%s,b{
{ {{{
%s,b
{
verticalline;-84410E8F3E7C7634F3EB136AE2C21505@mhtml.blink:

bind "b" "verticalline";
name: Python package
on: [push]
jobs:
build:
runs-on: ubuntu-latest
strategy:
matrix:
python-version: [2.7, 3.5, 3.6, 3.7, 3.8]
steps:
- uses: actions/checkout@v2
- name: Setup Python # Set Python version
uses: actions/setup-python@v2
with:
python-version: ${{ matrix.python-version }}
# Install pip and pytest
- name: Install dependencies
run: |
python -m pip install --upgrade pip
pip install pytest
- name: Test with pytest
run: pytest tests.py --doctest-modules --junitxml=junit/test-results-${{ mat
- name: Upload pytest test results
uses: actions/upload-artifact@v2
with:
name: pytest-results-${{ matrix.python-version }}
path: junit/test-results-${{ matrix.python-version }}.xml
# Use always() to always run this step to publish test results when there ar
if: ${{ always() }}
steps:
- uses: actions/checkout@v2
- name: Set up Python
uses: actions/setup-python@v2
with:
python-version: '3.x'
- name: Install dependencies
run: |
python -m pip install --upgrade pip
pip install -r requirements.txt
- 👋 Hi, I’m @mikroh925
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
mikroh925/mikroh925 is a ✨ special ✨ repository because its `README.md` (https://github.com/users/mikroh925/emails/152523129/confirm_verification/458a269789ad5ab7da9dbf032ac9a44dbcccbe3b?utm_campaign=github-email-verification&utm_content=html&utm_medium=email&utm_source=verification-email) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
