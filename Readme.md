# 拚乓球遊戲

## 使用HTML、CSS和JavaScript，並整合Bootstrap框架

<a href="https://alfo0924.github.io/20241108TableTennisWebGame/">拚乓球遊戲網址</a>


## 遊戲概述
這是一個經典的拚乓球遊戲，玩家控制左側球拍對戰右側的AI對手。遊戲使用滑鼠控制，簡單易上手，並具有計分系統。

## 主要功能特點

**遊戲介面**
- 響應式遊戲面板，適應不同螢幕大小
- 簡潔的計分顯示
- 流暢的動畫效果
- 現代化的視覺設計

**遊戲機制**
- 滑鼠控制玩家球拍
- 智能AI對手
- 球速隨遊戲進行逐漸加快
- 即時碰撞檢測
- 自動計分系統

## 程式碼結構解析

### HTML結構
```html
<div class="board">
    <div class="ball"></div>
    <div class="paddle" id="userPaddle"></div>
    <div class="paddle" id="aiPaddle"></div>
    <div class="score player-score">0</div>
    <div class="score ai-score">0</div>
    <div class="message">按空白鍵開始遊戲</div>
</div>
```

### CSS樣式特點
- 使用flexbox進行居中對齊
- 響應式設計（@media查詢）
- 現代化視覺效果（陰影、圓角等）
- 流暢的動畫效果

### JavaScript核心功能

**1. 遊戲初始化**
```javascript
let ballSpeedX = 5;
let ballSpeedY = 5;
let ballX = board.clientWidth / 2;
let ballY = board.clientHeight / 2;
let userPaddleY = 150;
let aiPaddleY = 150;
let gameState = 'start';
```

**2. 遊戲更新循環**
```javascript
function update() {
    if (gameState === 'play') {
        // 球的移動
        // 碰撞檢測
        // AI移動
        requestAnimationFrame(update);
    }
}
```

**3. 碰撞檢測系統**
- 檢測球與牆壁的碰撞
- 檢測球與球拍的碰撞
- 根據碰撞位置調整球的反彈角度

**4. AI控制邏輯**
```javascript
const aiSpeed = (ballY - (aiPaddleY + 50)) * 0.15;
aiPaddleY = Math.max(0, Math.min(board.clientHeight - 100, aiPaddleY + aiSpeed));
```

**5. 分數系統**
```javascript
function updateScore(winner) {
    if (winner === 'player') {
        playerScore.textContent = parseInt(playerScore.textContent) + 1;
    } else {
        aiScore.textContent = parseInt(aiScore.textContent) + 1;
    }
    resetBall();
}
```

## 技術特點

1. **響應式設計**
- 使用Bootstrap框架
- 自適應不同螢幕大小
- 流暢的移動端體驗

2. **效能優化**
- 使用requestAnimationFrame進行動畫更新
- 優化的碰撞檢測算法
- 平滑的運動控制

3. **遊戲平衡**
- 漸進式難度增加
- 智能AI對手行為
- 合理的物理運動模擬

## 操作說明
- 使用滑鼠上下移動控制左側球拍
- 按空白鍵開始遊戲
- 當球碰到對方牆壁時得分
- 球速會隨著遊戲進行而增加

這個遊戲程式碼結構清晰，易於理解和維護，同時提供了良好的遊戲體驗。使用了現代化的網頁技術，並考慮到了不同設備的適配性

