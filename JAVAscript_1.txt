// 画面サイズを取得
const screenWidth = window.innerWidth;
const screenHeight = window.innerHeight;

// 文字列の幅を取得
const textWidth = document.querySelector('.moving-text').clientWidth;

// 文字列の初期位置を設定
let textPositionX = (screenWidth - textWidth) / 2;
let textPositionY = screenHeight / 2;

// 文字列を移動させる関数
function moveText() {
    textPositionX++;
    if (textPositionX > screenWidth) {
        textPositionX = -textWidth;
    }
    document.querySelector('.moving-text').style.left = textPositionX + 'px';
    document.querySelector('.moving-text').style.top = textPositionY + 'px';
    requestAnimationFrame(moveText);
}

// ページが読み込まれたら文字列を移動させる
window.onload = function() {
    requestAnimationFrame(moveText);
}
