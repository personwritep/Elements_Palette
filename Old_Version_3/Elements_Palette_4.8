// ==UserScript==
// @name        Elements Palette ⭐
// @namespace        http://tampermonkey.net/
// @version        4.8
// @description        編集枠に各種要素を自動記入するツール
// @author        Ameba Blog User
// @match        https://blog.ameba.jp/ucs/entry/srventry*
// @exclude        https://blog.ameba.jp/ucs/entry/srventrylist.do*
// @icon        https://www.google.com/s2/favicons?sz=64&domain=ameblo.jp
// @grant        none
// @updateURL        https://github.com/personwritep/Elements_Palette/raw/main/Elements_Palette.user.js
// @downloadURL        https://github.com/personwritep/Elements_Palette/raw/main/Elements_Palette.user.js
// ==/UserScript==


let retry=0;
let interval=setInterval(wait_target, 100);
function wait_target(){
    retry++;
    if(retry>10){ // リトライ制限 10回 1sec
        clearInterval(interval); }
    let target=document.getElementById('cke_1_contents'); // 監視 target
    if(target){
        clearInterval(interval);
        main(); }}



function main(){
    let ua=0;
    let agent=window.navigator.userAgent.toLowerCase();
    if(agent.indexOf('firefox') > -1){ ua=1; } // Firefoxの場合のフラッグ



    let ep_preset=[]; // Elements Palette のユーザー設定

    let read_json=localStorage.getItem('EP_Preset'); // ローカルストレージ 保存名
    ep_preset=JSON.parse(read_json);
    if(ep_preset==null){
        ep_preset=[0, 2, "#2277dd", 0.6, "#4dffc9", 1, "#ff0000", 0, "#ffffff", 0, 0.5, 0]; }
    let write_json=JSON.stringify(ep_preset);
    localStorage.setItem('EP_Preset', write_json); // ローカルストレージ 保存



    let target=document.getElementById('cke_1_contents'); // 監視 target
    let monitor=new MutationObserver(catch_key);
    monitor.observe(target, {childList: true}); // ショートカット待受け開始

    catch_key();

    function catch_key(){
        document.addEventListener("keydown", check_key); // iframe外のキー取得

        let editor_iframe=document.querySelector('.cke_wysiwyg_frame');
        if(editor_iframe){ // iframe読込みが実行条件
            let iframe_doc=editor_iframe.contentWindow.document;
            iframe_doc.addEventListener("keydown", check_key); } // iframe内のキー取得


        let gate;

        function check_key(event){
            let send=-1;

            if(event.keyCode==19 && !event.shiftKey){ gate=1; } // 「Pause」キー入力
            else if(event.keyCode==19 && event.shiftKey){ gate=2; } // 「Pause+Shift」キー入力

            if(event.keyCode==112){
                if(gate==1){ event.preventDefault(); send=112; } // F1
                else if(gate==2){ event.preventDefault(); send=212; }} // F1 +Shift
            if(event.keyCode==113){
                if(gate==1){ event.preventDefault(); send=113; } // F2
                else if(gate==2){ event.preventDefault(); send=213; }} // F2 +Shift
            if(event.keyCode==114){
                if(gate==1){ event.preventDefault(); send=114; } // F3
                else if(gate==2){ event.preventDefault(); send=214; }} // F3 +Shift
            if(event.keyCode==115){
                if(gate==1){ event.preventDefault(); send=115; } // F4
                else if(gate==2){ event.preventDefault(); send=215; }} // F4 +Shift
            if(event.keyCode==116){
                if(gate==1){ event.preventDefault(); send=116; } // F5
                else if(gate==2){ event.preventDefault(); send=216; }} // F5 +Shift
            if(event.keyCode==117){
                if(gate==1){ event.preventDefault(); send=117; } // F6
                else if(gate==2){ event.preventDefault(); send=217; }} // F6 +Shift
            if(event.keyCode==118){
                if(gate==1){ event.preventDefault(); send=118; } // F7
                else if(gate==2){ event.preventDefault(); send=218; }} // F7 +Shift
            if(event.keyCode==119){
                if(gate==1){ event.preventDefault(); send=119; } // F8
                else if(gate==2){ event.preventDefault(); send=219; }} // F8 +Shift
            if(event.keyCode==120){
                if(gate==1){ event.preventDefault(); send=120; } // F9
                else if(gate==2){ event.preventDefault(); send=220; }} // F9 +Shift
            if(event.keyCode==121){
                if(gate==1){ event.preventDefault(); send=121; } // F10
                else if(gate==2){ event.preventDefault(); send=221; }} // F10 +Shift
            if(event.keyCode==122){
                if(gate==1){ event.preventDefault(); send=122; } // F11
                else if(gate==2){ event.preventDefault(); send=222; }} // F11 +Shift
            if(event.keyCode==123){
                if(gate==1){ event.preventDefault(); send=123; } // F12
                else if(gate==2){ event.preventDefault(); send=223; }} // F12 +Shift

            if(event.keyCode !=19){ gate=-1; }
            if(send !=-1){
                event.stopImmediatePropagation();
                set_mark(send); }

            if(event.keyCode==27){ //「ESC」でメニューを閉じる
                close_ep();
                close_eps(); }

        } // check_key

    } // catch_key



    function set_mark(sender){
        let editor_iframe;
        let iframe_doc;
        let iframe_html;
        let iframe_body;
        let selection;
        let range;
        let ac_node;
        let insert_node;

        editor_iframe=document.querySelector('.cke_wysiwyg_frame');
        iframe_doc=editor_iframe.contentWindow.document;
        iframe_html=iframe_doc.querySelector('html');
        iframe_body=iframe_doc.querySelector('body.cke_editable');
        selection=iframe_doc.getSelection();
        range=selection.getRangeAt(0);
        ac_node=selection.anchorNode;



        let help_url='https://ameblo.jp/personwritep/entry-12803137359.html';

        let help=
            '<a class="epalette_help" href="'+ help_url +'" target="_blank">'+
            '<svg width="20" height="24" viewBox="0 -20 150 150">'+
            '<path  fill="#fff" d="M66 13C56 15 47 18 39 24C-12 60 18 146 82 137C92 '+
            '135 102 131 110 126C162 90 128 4 66 13M68 25C131 17 145 117 81 '+
            '125C16 133 3 34 68 25M69 40C61 41 39 58 58 61C66 63 73 47 82 57C84 '+
            '60 83 62 81 65C77 70 52 90 76 89C82 89 82 84 86 81C92 76 98 74 100 66'+
            'C105 48 84 37 69 40M70 94C58 99 66 118 78 112C90 107 82 89 70 94z">'+
            '</path></svg></a>';



        if(sender==112){ // F1　　h2 見出しの自動記入
            let style_text='background: #b0e0e6; padding: .32em 1em .2em'; // h2のデザイン
            let font_size='font-size: 1em'; // h2のフォントサイズ

            let insert_node_h;
            let h_tag=
                '<h2 style="'+ font_size +'">'+
                '<span style="'+ style_text +'">\u200A</span></h2>';

            if(ac_node.nodeType==3 &&
               ac_node.parentNode.tagName=='P' &&
               ac_node.parentNode.parentNode.tagName=='BODY'){
                ac_node.parentNode.insertAdjacentHTML('beforebegin', h_tag);
                setTimeout(()=>{
                    insert_node_h=ac_node.parentNode.previousElementSibling;
                    h_before_after(insert_node_h);
                    h_when_end(insert_node_h);
                }, 20);
            } // h要素生成の条件 通常のP要素のテキストノードから作成

            if(ac_node.tagName=='P' &&
               ac_node.firstChild.tagName=="BR" && ac_node.parentNode.tagName=='BODY'){
                ac_node.insertAdjacentHTML('beforebegin', h_tag);
                setTimeout(()=>{
                    insert_node_h=ac_node.previousElementSibling;
                    h_before_after(insert_node_h);
                    h_when_end(insert_node_h);
                }, 20);
            } // h要素生成の条件 空白行から作成
        } // F1



        if(sender==113){ // F2　　h3 見出しの自動記入
            let style_text='background: #ddd; padding: .32em 1em .2em'; // h3のデザイン
            let font_size='font-size: 1em'; // h3のフォントサイズ

            let insert_node_h;
            let h_tag=
                '<h3 style="'+ font_size +'">'+
                '<span style="'+ style_text +'">\u200A</span></h3>';

            if(ac_node.nodeType==3 &&
               ac_node.parentNode.tagName=='P' &&
               ac_node.parentNode.parentNode.tagName=='BODY'){
                ac_node.parentNode.insertAdjacentHTML('beforebegin', h_tag);
                setTimeout(()=>{
                    insert_node_h=ac_node.parentNode.previousElementSibling;
                    h_before_after(insert_node_h);
                    h_when_end(insert_node_h);
                }, 20);
            } // h要素生成の条件 通常のP要素のテキストノードから作成

            if(ac_node.tagName=='P' &&
               ac_node.firstChild.tagName=='BR' && ac_node.parentNode.tagName=='BODY'){
                ac_node.insertAdjacentHTML('beforebegin', h_tag);
                setTimeout(()=>{
                    insert_node_h=ac_node.previousElementSibling;
                    h_before_after(insert_node_h);
                    h_when_end(insert_node_h);
                }, 20);
            } // h要素生成の条件 空白行から作成
        } // F2



        if(sender==114){ // F3　　修飾線の自動記入
            // アンダーラインのデザイン
            let style_text=
                'linear-gradient(transparent 1.22em, '+
                ep_preset[2] +' 0, '+ ep_preset[2] +' calc(1.22em + '+ ep_preset[1] +
                'px), transparent 0)';
            insert_node=document.createElement('span');
            insert_node.style.background=style_text;

            try{
                range.surroundContents(insert_node); }
            catch(e){;}
        } // F3



        if(sender==115){ // F4　　修飾線の自動記入
            // マーカー線のデザイン
            let style_text=
                'linear-gradient(transparent '+ (1.22 - ep_preset[3]) +'em, '+
                ep_preset[4] +' 0, '+ ep_preset[4] +' 1.22em, transparent 0)';
            insert_node=document.createElement('span');
            insert_node.style.background=style_text;

            try{
                range.surroundContents(insert_node); }
            catch(e){;}
        } // F4



        if(sender==116){ // F5
            alert('【 F5 】 はショートカット無効です \n⛔ページリロードに注意してください');
        } // F5



        if(sender==117){ // F6　　囲み枠の自動生成
            // 囲み枠のデザイン
            let insert_node_d;
            let d_tag;
            let d_style // 外部要素
            let c_style; // 内部要素
            let pad;
            let fit;

            if(ep_preset[11]==0){ // 通常サイズ枠
                if(ep_preset[9]==0){ // 幅フィットなし
                    pad='.62em 1.5em .5em';
                    fit=''; }
                else{ // 幅フィット
                    pad='.62em 0.6em .5em';
                    fit='width: fit-content'; }
                if(ep_preset[5]!=-1){
                    d_style='border: '+ ep_preset[5] +'px solid '+ ep_preset[6] +
                        '; border-radius: '+ ep_preset[7] +'px; padding: '+ pad +'; '+
                        'max-width: 660px; margin: 0.6em 0; line-height: 1.5;'+
                        'background: '+ ep_preset[8] +'; '+ fit; }
                else{
                    d_style='border: 3px double '+ ep_preset[6] +
                        '; border-radius: '+ ep_preset[7] +'px; padding: '+ pad +'; '+
                        'max-width: 660px; margin: 0.6em 0; line-height: 1.5;'+
                        'background: '+ ep_preset[8] +'; '+ fit; }
                d_tag=
                    '<div style="'+ d_style +'"><br></div>'; }

            else{ // 小型
                if(ep_preset[9]==0){ // 幅フィットなし
                    pad='3px 1.5em 1px; display: block'; }
                else{ // 幅フィット
                    pad='3px 0.6em 1px'; }
                d_style='margin: 0.6em 0;';
                if(ep_preset[5]!=-1){
                    c_style='border: '+ ep_preset[5] +'px solid '+ ep_preset[6] +
                        '; border-radius: '+ ep_preset[7] +'px; padding: '+ pad +'; '+
                        'max-width: 660px; background: '+ ep_preset[8] +'; '+
                        'line-height: 1.5;'; }
                else{
                    c_style='border: 3px double '+ ep_preset[6] +
                        '; border-radius: '+ ep_preset[7] +'px; padding: '+ pad +'; '+
                        'max-width: 660px; background: '+ ep_preset[8] +'; '+
                        'line-height: 1.5;'; }
                d_tag=
                    '<div style="'+ d_style +'">'+
                    '<span style="'+ c_style +'"><br></span></div>'; }


            if(ac_node.nodeType==3 &&
               ac_node.parentNode.tagName=='P'){
                ac_node.parentNode.insertAdjacentHTML('afterend', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.parentNode.nextElementSibling;
                    if(ep_preset[11]==0){ // 通常サイズ枠
                        d_before_after(insert_node_d, 0); }
                    else{ // 小型枠
                        d_before_after(insert_node_d, 1); }
                    d_when_end(insert_node_d);
                }, 20);
            } // d要素生成の条件 通常のP要素のテキストノードから作成

            if(ac_node.tagName=='P' &&
               ac_node.firstChild.tagName=='BR'){
                ac_node.insertAdjacentHTML('beforebegin', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.previousElementSibling;
                    if(ep_preset[11]==0){ // 通常サイズ枠
                        d_before_after(insert_node_d, 0); }
                    else{ // 小型枠
                        d_before_after(insert_node_d, 1); }
                    d_when_end(insert_node_d);
                }, 20);
            } // div要素生成の条件 空白行から作成
        } // F6



        if(sender==118){ // F7　　PRE枠の自動生成
            // PRE枠のデザイン 縦スクロールしないタイプ
            let style_text_div=' max-width: 620px; overflow-y: hidden; margin: 0.6em auto; '+
                'background: #fafafa; border: 1px solid #aaa;';
            let style_text_pre='white-space: pre; display: inline-block; padding: 0 2em;';

            let insert_node_d;
            let d_tag=
                '<div style="'+ style_text_div +'">'+
                '<pre style="'+ style_text_pre +'"><br></pre></div>';

            if(ac_node.nodeType==3 &&
               ac_node.parentNode.tagName=='P' &&
               ac_node.parentNode.parentNode.tagName=='BODY'){
                ac_node.parentNode.insertAdjacentHTML('afterend', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.parentNode.nextElementSibling;
                    d_before_after(insert_node_d, 1);
                    d_when_end(insert_node_d);
                }, 20);
            } // div要素生成の条件 通常のP要素のテキストノードから作成

            if(ac_node.tagName=='P' &&
               ac_node.firstChild.tagName=='BR' && ac_node.parentNode.tagName=='BODY'){
                ac_node.insertAdjacentHTML('beforebegin', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.previousElementSibling;
                    d_before_after(insert_node_d, 1);
                    d_when_end(insert_node_d);
                }, 20);
            } // div要素生成の条件 空白行から作成
        } // F7



        if(sender==119){ // F8　　PRE枠の自動生成
            // PRE枠のデザイン 縦スクロールするタイプ
            let style_text_div=' max-width: 620px; overflow: auto; height: 50vh; '+
                'margin: 0.6em auto; background: #fafafa; border: 1px solid #aaa; resize: vertical;';
            let style_text_pre='white-space: pre; display: inline-block; padding: 0 2em;';

            let insert_node_d;
            let d_tag=
                '<div style="'+ style_text_div +'">'+
                '<pre style="'+ style_text_pre +'"><br></pre></div>';

            if(ac_node.nodeType==3 &&
               ac_node.parentNode.tagName=='P' &&
               ac_node.parentNode.parentNode.tagName=='BODY'){
                ac_node.parentNode.insertAdjacentHTML('afterend', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.parentNode.nextElementSibling;
                    d_before_after(insert_node_d, 1);
                    d_when_end(insert_node_d);
                }, 20);
            } // div要素生成の条件 通常のP要素のテキストノードから作成

            if(ac_node.tagName=='P' &&
               ac_node.firstChild.tagName=='BR' && ac_node.parentNode.tagName=='BODY'){
                ac_node.insertAdjacentHTML('beforebegin', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.previousElementSibling;
                    d_before_after(insert_node_d, 1);
                    d_when_end(insert_node_d);
                }, 20);
            } // div要素生成の条件 空白行から作成
        } // F8



        if(sender==120){ // F9　　文書末尾に空白行を追加
            if(iframe_body.lastChild.tagName !='P' && iframe_body.lastChild.tagName !='STYLE'){
                add_nextline();
                add_nextline(); }
            else if(iframe_body.lastChild.tagName=='P'){
                if(iframe_body.lastChild.style.textAlign=='center'
                   || iframe_body.lastChild.style.textAlign=='right'){
                    add_nextline();
                    add_nextline(); }}
            else if(iframe_body.lastChild.tagName=='STYLE'){
                if(iframe_body.lastChild.className=='asa'){
                    add_preline();
                    add_preline(); }}

            range.collapse(); // rangeを始点で閉じる
            iframe_html.scrollTop=iframe_html.scrollHeight;

            function add_nextline(){
                insert_node=iframe_doc.createElement('p');
                insert_node.appendChild(iframe_doc.createTextNode('\u00A0'));
                iframe_body.appendChild(insert_node);
                range.setEnd(insert_node.lastChild, 0); } // 追加した空白行にrange終点を移動

            function add_preline(){
                insert_node=iframe_doc.createElement('p');
                insert_node.appendChild(iframe_doc.createTextNode('\u00A0'));
                iframe_body.insertBefore(insert_node, iframe_body.lastChild);
                range.setEnd(insert_node.lastChild, 0); } // 追加した空白行にrange終点を移動
        } // F9



        if(sender==121){ // F10　　行間隔の狭い空白行の挿入
            if(ac_node!=iframe_body.lastChild){ // 文末では禁（通常の改行が作れなくなる）
                if(ac_node.tagName=='P' && ac_node.firstChild.tagName=="BR" &&
                   ac_node.childElementCount==1){
                    // 空白行のみを対象に半改行にする
                    ac_node.style.lineHeight=ep_preset[10]+'em'; }}
            else{
                alert('文末の空白行は標準の行間隔が適当です'); }
        } // F10



        if(sender==122){ // F11　　選択範囲の「カギ括弧」⇄「半角カギ括弧」の変換
            //  '｢' (\uFF62)  '｣' (\uFF63) の文字へ置換え
            let r_text=range.toString();

            if(r_text.match( /「|」/ ) !=null){
                r_text=r_text.replace(/「/g, '\u2006｢').replace(/」/g, '｣\u2006');
                let insert_node=document.createTextNode(r_text);
                try{
                    range.surroundContents(insert_node); }
                catch(e){;}}
            else{
                if(r_text.match( /\u2006｢|｣\u2006|｢|｣/ ) !=null){
                    r_text=r_text.replace(/\u2006｢/g, '「').replace(/｣\u2006/g, '」')
                        .replace(/｣/g, '」').replace(/｢/g, '「');
                    let insert_node=document.createTextNode(r_text);
                    try{
                        range.surroundContents(insert_node); }
                    catch(e){;}}}
        } // F11



        if(sender==123){ // F12　　「Elements Palette」のメニュー表示
            let ep_style=
                '<style>'+
                '.ep_menu { position: absolute; top: 10px; right: 20px; z-index: 15; '+
                'font: 16px/26px Meiryo; width: 360px; padding: .6em 1em; '+
                'border: 1px solid #009688; border-radius: 4px; '+
                'background: #f9fafa; box-shadow: 6px 6px 20px rgba(0, 0, 0, 0.3); } '+
                '.mh { font: bold 18px Meiryo;  color: #fff; background: #2196f3; '+
                'text-align: center; padding: 3px 0 0; margin-bottom: 8px; } '+
                '.epalette_help { position: absolute; top: 11px; left: 24px; } '+
                '.ep_close { position: absolute; top: 14px; right: 24px; height: 20px; '+
                'line-height: 24px; padding: 0 2px; border: 1px solid #fff; '+
                'border-radius: 3px; cursor: pointer; } '+
                '.ep_menu input { height: 18px; font-family: system-ui; text-align: center; } '+
                '#F3w { width: 30px; margin-right: 8px; } #F4w { width: 38px; } '+
                '#F6w { width: 28px; } #F6r { width: 34px; } '+
                '#F6f, #F6s { margin-right: 4px; vertical-align: -3px; cursor: pointer; } '+
                '#F3c, #F4c, #F6c, #F6b { height: 26px; width: 22px; border: none; '+
                'background: none; vertical-align: -3px; cursor: pointer; } #F10 { width: 40px; } ';

            if(ua==1){
                ep_style+=
                    '#F3w, #F6w { width: 34px; } #F4w, #F10 { width: 44px; } '+
                    '#F6r { width: 38px; } #F6f, #F6s { vertical-align: -1px; } '+
                    '#F3c, #F4c, #F6c, #F6b { height: 18px; width: 18px; } '; }

            ep_style+='</style>';


            let menu=
                '<div class="ep_menu">'+
                '<p class="mh">'+ help +'〔 Elements Palette Menu 〕'+
                '<span class="ep_close">✖</span></p>'+
                'Pause ➔ F1　　h2 見出し<br>'+
                'Pause ➔ F2　　h3 見出し<br>'+
                'Pause ➔ F3　　アンダーライン　　<br>　　　　　　　　線幅 '+
                '<input id="F3w" type="number" step="1" min="1" max="4">'+
                '　線色 <input id="F3c" type="color"><br>'+
                'Pause ➔ F4　　マーカー線　　　　<br>　　　　　　　　線幅 '+
                '<input id="F4w" type="number" step="0.1" step="0.1" min="0.1" max="1.2">'+
                '　線色 <input id="F4c" type="color"><br>'+
                'Pause ➔ F5　　（無効）<br>'+
                'Pause ➔ F6　　囲み枠　<input id="F6f" type="checkbox">幅フィット'+
                '　<input id="F6s" type="checkbox">小型<br>'+
                '　　　　　　　　幅 <input id="F6w" type="number" step="1" min="-1" max="9">'+
                ' <input id="F6c" type="color">'+
                ' 角 <input id="F6r" type="number" step="1" min="0" max="20">'+
                ' 背景色 <input id="F6b" type="color"><br>'+
                'Pause ➔ F7　　PRE枠<br>'+
                'Pause ➔ F8　　PRE枠（スクロールタイプ）<br>'+
                'Pause ➔ F9　　文書末尾に空白行追加<br>'+
                'Pause ➔ F10　 空白行に行間隔を指定　 '+
                '<input id="F10" type="number" step="0.1" min="0" max="3"><br>'+
                'Pause ➔ F11　「カギ括弧」全角 ⇄ 半角 変換<br>'+
                'Pause ➔ F12　「Elements Palette」メニュー<br>'+
                '<br>'+
                '<p class="mh">〔 Fixed Format Palette Menu 〕</p>'+
                'Alt + F11　　　通常表示で選択範囲を登録<br>'+
                '　　　　　※Chrome/EdgeはHTML登録が可能<br>'+
                'Ctrl + F11 　　 通常表示で登録内容をペースト'+
                ep_style +'</div>';


            if(!document.querySelector('.ep_menu')){
                document.querySelector('.l-body').insertAdjacentHTML('beforeend', menu);
                close_eps(); }
            else{
                close_ep(); }



            let F3w=document.querySelector('#F3w');
            if(F3w){
                F3w.value=ep_preset[1];

                F3w.addEventListener("input", function(){
                    ep_preset[1]=parseFloat(F3w.value);
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F3c=document.querySelector('#F3c');
            if(F3c){
                F3c.value=ep_preset[2];

                F3c.addEventListener("change", function(){
                    ep_preset[2]=F3c.value;
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F4w=document.querySelector('#F4w');
            if(F4w){
                F4w.value=ep_preset[3];

                F4w.addEventListener("input", function(){
                    ep_preset[3]=parseFloat(F4w.value);
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F4c=document.querySelector('#F4c');
            if(F4c){
                F4c.value=ep_preset[4];

                F4c.addEventListener("change", function(){
                    ep_preset[4]=F4c.value;
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F6w=document.querySelector('#F6w');
            if(F6w){
                F6w.value=ep_preset[5];

                F6w.addEventListener("input", function(){
                    ep_preset[5]=parseFloat(F6w.value);
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F6c=document.querySelector('#F6c');
            if(F6c){
                F6c.value=ep_preset[6];

                F6c.addEventListener("change", function(){
                    ep_preset[6]=F6c.value;
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F6r=document.querySelector('#F6r');
            if(F6r){
                F6r.value=ep_preset[7];

                F6r.addEventListener("input", function(){
                    ep_preset[7]=parseFloat(F6r.value);
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F6b=document.querySelector('#F6b');
            if(F6b){
                F6b.value=ep_preset[8];

                F6b.addEventListener("change", function(){
                    ep_preset[8]=F6b.value;
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F6f=document.querySelector('#F6f');
            if(F6f){
                if(ep_preset[9]==0){
                    F6f.checked=false; }
                else{
                    F6f.checked=true; }

                F6f.addEventListener("change", function(){
                    if(F6f.checked==true){
                        ep_preset[9]=1; }
                    else{
                        ep_preset[9]=0; }
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F6s=document.querySelector('#F6s');
            if(F6s){
                if(ep_preset[11]==0){
                    F6s.checked=false; }
                else{
                    F6s.checked=true; }

                F6s.addEventListener("change", function(){
                    if(F6s.checked==true){
                        ep_preset[11]=1; }
                    else{
                        ep_preset[11]=0; }
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }


            let F10=document.querySelector('#F10');
            if(F10){
                F10.value=ep_preset[10];

                F10.addEventListener("input", function(){
                    ep_preset[10]=parseFloat(F10.value);
                    let write_json=JSON.stringify(ep_preset);
                    localStorage.setItem('EP_Preset', write_json); }); }
        } // F12




        if(sender==212){ // F1 +Shift　　Font Awesome リンクアイコンの自動記入
            let insert_node_z;
            insert_node=iframe_doc.createElement('i');
            insert_node.appendChild(iframe_doc.createTextNode('\u00A0'));
            insert_node.setAttribute('class', 'fas fa-external-link-alt fa-sm');
            insert_node.setAttribute('style', 'margin-left: .5em');
            range.insertNode(insert_node);

            insert_node_z=iframe_doc.createTextNode('\u200A');
            insert_node.parentNode.insertBefore(insert_node_z, insert_node.nextSibling);
            range.setEnd(insert_node_z.nextSibling, 0);
            range.collapse(); // フォーカスを失わないでrangeを閉じる
        } // F1 +Shift



        if(sender==213){ // F2 +Shift　　Font Awesome リロードアイコンの自動記入
            let insert_node_z;
            insert_node=iframe_doc.createElement('i');
            insert_node.appendChild(iframe_doc.createTextNode('\u00A0'));
            insert_node.setAttribute('class', 'fa-solid fa-arrow-rotate-right');
            insert_node.setAttribute('style', 'margin-left: .5em');
            range.insertNode(insert_node);

            insert_node_z=iframe_doc.createTextNode('\u200A');
            insert_node.parentNode.insertBefore(insert_node_z, insert_node.nextSibling);
            range.setEnd(insert_node_z.nextSibling, 0);
            range.collapse(); // フォーカスを失わないでrangeを閉じる
        } // F2 +Shift



        if(sender==214){ // F3 +Shift　　Font Awesome ペンアイコンの自動記入
            let insert_node_z;
            insert_node=iframe_doc.createElement('i');
            insert_node.appendChild(iframe_doc.createTextNode('\u00A0'));
            insert_node.setAttribute('class', 'fa-solid fa-pen');
            insert_node.setAttribute('style', 'margin-left: .5em');
            range.insertNode(insert_node);

            insert_node_z=iframe_doc.createTextNode('\u200A');
            insert_node.parentNode.insertBefore(insert_node_z, insert_node.nextSibling);
            range.setEnd(insert_node_z.nextSibling, 0);
            range.collapse(); // フォーカスを失わないでrangeを閉じる
        } // F3 +Shift



        if(sender==215){ // F4 +Shift　　鍵アイコンの自動記入
            let insert_node_z;
            insert_node=iframe_doc.createElement('i');
            insert_node.appendChild(iframe_doc.createTextNode('\u00A0'));
            insert_node.setAttribute('class', 'fa-solid fa-lock');
            insert_node.setAttribute('style', 'margin-left: .5em');
            range.insertNode(insert_node);

            insert_node_z=iframe_doc.createTextNode('\u200A');
            insert_node.parentNode.insertBefore(insert_node_z, insert_node.nextSibling);
            range.setEnd(insert_node_z.nextSibling, 0);
            range.collapse(); // フォーカスを失わないでrangeを閉じる
        } // F4 +Shift



        if(sender==216){ // F5 +Shift
            alert('【 F5 】 はショートカット無効です \n⛔ページリロードに注意してください');
        } // F5 +Shift



        if(sender==217){ // F6 +Shift　　リブログカードをデザイン
            let style_dtext=
                'max-width: 500px; height: 140px; margin: 0 auto; border: 1px solid #009688; '+
                'border-radius: 4px; overflow: hidden; transition: .5s;';
            let style_itext='max-width: unset; width: calc(100% + 30px); '+
                'margin: -45px -15px 0; background: #f0f7fb;';

            let rebrog;
            let insert_node_d;
            rebrog=iframe_doc.querySelector('.reblogCard');

            if(rebrog){
                insert_node_d=iframe_doc.createElement('div');

                if(rebrog.parentNode.tagName=='P'){
                    iframe_body.insertBefore(insert_node_d, rebrog.parentNode);
                    insert_node_d.appendChild(rebrog); }
                if(rebrog.parentNode.tagName=='DIV'){
                    rebrog.parentNode.setAttribute('style', style_dtext);
                    rebrog.parentNode.setAttribute('class', 'rlink');
                    rebrog.setAttribute('style', style_itext); }

                if(rebrog.parentNode.previousElementSibling==null){ //ページ最上部なら上に余白行追加
                    insert_node_d.insertAdjacentHTML('beforebegin', '<p>\u00A0</p><p>\u00A0</p>');}
                if(rebrog.parentNode.nextElementSibling==rebrog.parentNode.parentNode.lastChild){
                    rebrog.parentNode.insertAdjacentHTML('afterend', '<p>\u00A0</p>'); }} //文末処理
        } // F6 +Shift



        if(sender==218){ // F7 +Shift
        } // F7 +Shift



        if(sender==219){ // F8 +Shift
        } // F8 +Shift



        if(sender==220){ // F9 +Shift
        } // F9 +Shift



        if(sender==221){ // F10 +Shift
        } // F10 +Shift



        if(sender==222){ // F11 +Shift　　HTMLデータのペースト
            let insert_node_d;
            let d_tag='<div id="p_clip">\u0020</div>';

            // div要素生成の条件　通常のP要素またはDIV要素のテキストノードから作成
            if(ac_node.nodeType==3 &&
               (ac_node.parentNode.tagName=='P' || ac_node.parentNode.tagName=='DIV')){
                ac_node.parentNode.insertAdjacentHTML('afterend', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.parentNode.nextElementSibling;
                    d_before_after(insert_node_d, 1);
                    d_when_end(insert_node_d);
                }, 20); }

            // div要素生成の条件 空白行から作成
            else if(ac_node.tagName=='P' &&
                    ac_node.firstChild.tagName=='BR'){
                ac_node.insertAdjacentHTML('beforebegin', d_tag);
                setTimeout(()=>{
                    insert_node_d=ac_node.previousElementSibling;
                    d_before_after(insert_node_d, 1);
                    d_when_end(insert_node_d);
                }, 20); }

            let core=iframe_doc.querySelector('#p_clip');
            if(core){
                if(navigator.clipboard){
                    navigator.clipboard.readText()
                        .then(function(text){
                        core.outerHTML=text; }); }}
        } // F11 +Shift



        if(sender==223){ // F12 +Shift　　「Elements Palette +Shift」のメニュー表示
            let eps_style=
                '<style>'+
                '.eps_menu { position: absolute; top: 10px; right: 20px; z-index: 15; '+
                'font: 16px/26px Meiryo; width: 360px; padding: .6em 1em; '+
                'border: 1px solid #009688; border-radius: 4px; '+
                'background: #f9fafa; box-shadow: 6px 6px 20px rgba(0, 0, 0, 0.3); } '+
                '.mh { font: bold 18px Meiryo;  color: #fff; background: #2196f3; '+
                'text-align: center; padding: 3px 0 0; margin-bottom: 8px; } '+
                '.epalette_help { position: absolute; top: 11px; left: 24px; } '+
                '.ep_close { position: absolute; top: 14px; right: 24px; height: 20px; '+
                'line-height: 24px; padding: 0 2px; border: 1px solid #fff; '+
                'border-radius: 3px; cursor: pointer; } '+
                '</style>';

            let menu_s=
                '<div class="eps_menu">'+
                '<p class="mh">'+ help +'〔 Elements Palette Menu 〕'+
                '<span class="ep_close">✖</span></p>'+
                'Pause+Shift ➔ F1　　リンクアイコン<br>'+
                'Pause+Shift ➔ F2　　リロードアイコン<br>'+
                'Pause+Shift ➔ F3　　ペンアイコン<br>'+
                'Pause+Shift ➔ F4　　鍵アイコン<br>'+
                'Pause+Shift ➔ F5　　（無効）<br>'+
                'Pause+Shift ➔ F6　　リブログカードを修飾<br>'+
                'Pause+Shift ➔ F7　　<br>'+
                'Pause+Shift ➔ F8　　<br>'+
                'Pause+Shift ➔ F9　　<br>'+
                'Pause+Shift ➔ F10　 <br>'+
                'Pause+Shift ➔ F11　 HTMLデータのペースト<br>'+
                'Pause+Shift ➔ F12　 サブメニュー<br>'+
                eps_style +'</div>';

            if(!document.querySelector('.eps_menu')){
                document.querySelector('.l-body').insertAdjacentHTML('beforeend', menu_s);
                close_ep(); }
            else{
                close_eps(); }
        } // F12 +Shift




        function h_before_after(insert_node_h){
            if(insert_node_h.previousElementSibling !=null &&
               insert_node_h.previousElementSibling.firstChild.tagName !='BR'){
                insert_node_h.insertAdjacentHTML('beforebegin', '<p>\u00A0</p>');}
            if(insert_node_h.nextElementSibling.firstChild.tagName !='BR'){
                insert_node_h.insertAdjacentHTML('afterend', '<p>\u00A0</p>');}
            range.setEnd(insert_node_h.lastChild, 0);} // 生成したh要素の前後の空白行処理


        function h_when_end(insert_node_h){
            if(insert_node_h.nextElementSibling==insert_node_h.parentNode.lastChild){
                insert_node_h.insertAdjacentHTML('afterend', '<p>\u00A0</p>');
                iframe_html.scrollTop=iframe_html.scrollHeight;}} // 文末処理


        function d_before_after(insert_node_d, nest){
            if(insert_node_d==insert_node_d.parentNode.firstChild ||
               insert_node_d.previousElementSibling.firstChild.tagName !='BR'){
                insert_node_d.insertAdjacentHTML('beforebegin', '<p>\u00A0</p>'); }
            if(insert_node_d.nextElementSibling==null ||
               insert_node_d.nextElementSibling.firstChild.tagName !='BR'){
                insert_node_d.insertAdjacentHTML('afterend', '<p>\u00A0</p>'); }
            if(nest==0){
                range.setEnd(insert_node_d, 0); }
            else{
                range.setEnd(insert_node_d.firstChild, 0); }
            range.collapse(); } // 生成したdiv要素の前後の空白行処理


        function d_when_end(insert_node_d){
            if(insert_node_d.nextElementSibling==insert_node_d.parentNode.lastChild){
                insert_node_d.insertAdjacentHTML('afterend', '<p>\u00A0</p>');
                iframe_html.scrollTop=iframe_html.scrollHeight; }} // 文末処理



        let ep_close=document.querySelector('.ep_close');
        if(ep_close){
            ep_close.onclick=()=>{
                close_ep();
                close_eps(); }}

    } // set_mark




    function close_ep(){ // メインメニューを閉じる
        let ep=document.querySelector('.ep_menu');
        if(ep){
            ep.remove(); }}

    function close_eps(){ // サブメニューを閉じる
        let eps=document.querySelector('.eps_menu');
        if(eps){
            eps.remove(); }}

} // main()
