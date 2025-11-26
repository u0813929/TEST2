<!DOCTYPE html>
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>網頁版碼錶</title>
    <style>
        /* --- CSS 樣式 --- */
        body {
            font-family: 'Microsoft JhengHei', sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .container {
            background-color: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            text-align: center;
            width: 90%;
            max-width: 500px;
        }

        .time-display {
            font-family: 'Courier New', Courier, monospace;
            font-size: 4rem;
            font-weight: bold;
            color: #333;
            margin-bottom: 30px;
            background-color: #fafafa;
            padding: 20px;
            border-radius: 8px;
            border: 1px solid #ddd;
        }

        .controls {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        button {
            font-family: 'Microsoft JhengHei', sans-serif;
            font-size: 1.1rem;
            padding: 10px 25px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.2s, transform 0.1s;
            min-width: 100px;
        }

        button:active {
            transform: scale(0.98);
        }

        /* 按鈕特定樣式 */
        #startBtn {
            background-color: #4CAF50; /* 綠色 */
            color: white;
        }
        #startBtn:disabled {
            background-color: #a5d6a7;
            cursor: not-allowed;
            transform: none;
        }

        #stopBtn {
            background-color: #f44336; /* 紅色 */
            color: white;
        }
        #stopBtn:disabled {
            background-color: #ef9a9a;
            cursor: not-allowed;
            transform: none;
        }

        #resetBtn {
            background-color: #2196F3; /* 藍色 */
            color: white;
        }
        #resetBtn:disabled {
            background-color: #90caf9;
            cursor: not-allowed;
            transform: none;
        }

        /* 響應式設計：手機版字體縮小 */
        @media (max-width: 480px) {
            .time-display {
                font-size: 2.5rem;
            }
            button {
                padding: 10px 15px;
                min-width: 80px;
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- 時間顯示區域 -->
        <div class="time-display" id="display">00:00:00</div>

        <!-- 控制按鈕區域 -->
        <div class="controls">
            <button id="startBtn">開始</button>
            <button id="stopBtn" disabled>暫停</button>
            <button id="resetBtn" disabled>重設</button>
        </div>
    </div>

    <script>
        /* --- JavaScript 邏輯 --- */
        
        // 取得 DOM 元素
        const display = document.getElementById('display');
        const startBtn = document.getElementById('startBtn');
        const stopBtn = document.getElementById('stopBtn');
        const resetBtn = document.getElementById('resetBtn');

        // 狀態變數
        let startTime = 0;
        let elapsedTime = 0;
        let timerInterval = null;
        let isRunning = false;

        // 格式化時間函數
        function formatTime(ms) {
            // 計算分鐘、秒、百分之一秒 (10ms)
            // 1 分鐘 = 60000 毫秒
            const minutes = Math.floor(ms / 60000);
            
            // 1 秒 = 1000 毫秒
            const seconds = Math.floor((ms % 60000) / 1000);
            
            // 百分之一秒 (取前兩位)
            const hundredths = Math.floor((ms % 1000) / 10);

            // 補零並組合成字串
            const minStr = minutes.toString().padStart(2, '0');
            const secStr = seconds.toString().padStart(2, '0');
            const hundStr = hundredths.toString().padStart(2, '0');

            return `${minStr}:${secStr}:${hundStr}`;
        }

        // 更新顯示函數
        function updateDisplay() {
            // 計算當前經過的總時間
            const currentTime = Date.now();
            const timeDiff = currentTime - startTime + elapsedTime;
            
            display.textContent = formatTime(timeDiff);
        }

        // 開始按鈕事件
        startBtn.addEventListener('click', () => {
            if (!isRunning) {
                isRunning = true;
                startTime = Date.now();
                
                // 啟動計時器，每 10ms 更新一次 (模擬 100Hz)
                timerInterval = setInterval(updateDisplay, 10);

                // 更新按鈕狀態
                startBtn.disabled = true;
                stopBtn.disabled = false;
                resetBtn.disabled = true;
                
                // 改變文字為「繼續」 (為了下次暫停後顯示)
                startBtn.textContent = "繼續";
            }
        });

        // 暫停按鈕事件
        stopBtn.addEventListener('click', () => {
            if (isRunning) {
                isRunning = false;
                clearInterval(timerInterval);
                
                // 累加經過的時間
                elapsedTime += Date.now() - startTime;
                
                // 更新按鈕狀態
                startBtn.disabled = false;
                stopBtn.disabled = true;
                resetBtn.disabled = false;
            }
        });

        // 重設按鈕事件
        resetBtn.addEventListener('click', () => {
            isRunning = false;
            clearInterval(timerInterval);
            
            // 重置變數
            elapsedTime = 0;
            startTime = 0;
            
            // 重置顯示
            display.textContent = "00:00:00";
            
            // 更新按鈕狀態
            startBtn.disabled = false;
            stopBtn.disabled = true;
            resetBtn.disabled = true;
            
            // 恢復文字為「開始」
            startBtn.textContent = "開始";
        });

    </script>
</body>
</html>
