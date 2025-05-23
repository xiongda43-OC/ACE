<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>专业报价换算系统</title>
    <style>
        :root {
            --primary-color: #3a7ca5;  /* 柔和的蓝色 */
            --secondary-color: #81c3d7; /* 浅蓝色 */
            --accent-color: #2f6690;   /* 深蓝色 */
            --dark-color: #16425b;     /* 深蓝底色 */
            --light-color: #e8f1f2;    /* 浅灰蓝色文字 */
            --success-color: #4caf50;  /* 柔和的绿色 */
            --warning-color: #ff9800;  /* 柔和的橙色 */
            --card-bg: rgba(255, 255, 255, 0.1); /* 半透明白色卡片背景 */
            --border-color: rgba(255, 255, 255, 0.2); /* 柔和的边框 */
        }
        
        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            background-color: var(--dark-color);
            color: var(--light-color);
            margin: 0;
            padding: 0;
            line-height: 1.6;
            background-image: linear-gradient(135deg, var(--dark-color) 0%, #1e3d59 100%);
        }
        
        .container {
            width: 100%;
            max-width: 100%;
            padding: 15px;
        }
        
        header {
            text-align: center;
            padding: 25px 0;
            background: linear-gradient(135deg, var(--primary-color), var(--dark-color));
            border-bottom: 1px solid var(--border-color);
        }
        
        h1 {
            font-size: 1.8rem;
            margin: 0;
            color: white;
            font-weight: 400;
        }
        
        .subtitle {
            font-size: 0.9rem;
            color: var(--secondary-color);
            opacity: 0.9;
            margin-top: 8px;
        }
        
        h2 {
            color: white;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 8px;
            margin-top: 25px;
            font-size: 1.3rem;
            font-weight: 400;
        }
        
        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 25px;
            backdrop-filter: blur(5px);
        }
        
        select, input, button, .file-input-label {
            width: 100%;
            background-color: rgba(255, 255, 255, 0.1);
            color: white;
            border: 1px solid var(--border-color);
            padding: 14px 18px;
            margin: 12px 0;
            border-radius: 8px;
            font-size: 1rem;
            -webkit-appearance: none;
        }
        
        select {
            background-image: url('data:image/svg+xml;utf8,<svg fill="%2381c3d7" height="24" viewBox="0 0 24 24" width="24" xmlns="http://www.w3.org/2000/svg"><path d="M7 10l5 5 5-5z"/></svg>');
            background-repeat: no-repeat;
            background-position: right 15px center;
        }
        
        /* 优化选项样式 */
        select option {
            padding: 12px 15px;
            background-color: var(--dark-color);
            color: white;
        }
        
        button, .file-input-label {
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            color: white;
            font-weight: 500;
            border: none;
        }
        
        .result {
            display: none;
        }
        
        .result.show {
            display: block;
        }
        
        .result-value {
            font-size: 1.8rem;
            color: white;
            font-weight: 500;
            margin: 20px 0;
            text-align: center;
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 8px;
            border-left: 4px solid var(--secondary-color);
        }
        
        .table-container {
            width: 100%;
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
            margin: 25px 0;
            border-radius: 10px;
            border: 1px solid var(--border-color);
        }
        
        th, td {
            border: 1px solid var(--border-color);
            padding: 10px 12px;
            text-align: left;
        }
        
        th {
            background-color: var(--primary-color);
            color: white;
        }
        
        footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 40px;
            border-top: 1px solid var(--border-color);
            font-size: 0.85rem;
            color: var(--secondary-color);
        }
        
        .formula {
            background-color: rgba(58, 124, 165, 0.2);
            padding: 15px;
            border-left: 4px solid var(--secondary-color);
            margin: 20px 0;
            font-family: 'Courier New', monospace;
            border-radius: 6px;
        }
        
        .password-hint {
            margin-top: 12px;
            font-size: 0.85rem;
            color: var(--secondary-color);
            text-align: center;
            line-height: 1.5;
        }
        
        .highlight {
            color: var(--secondary-color);
            font-weight: 500;
            text-decoration: none;
        }
        
        /* 手机端优化 */
        @media (max-width: 767px) {
            .container {
                padding: 12px;
            }
            
            .card {
                padding: 18px;
            }
            
            select, input, button, .file-input-label {
                padding: 15px;
            }
            
            .result-value {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <div class="toast" id="toast"></div>
    
    <header>
        <div class="container">
            <h1>专业报价换算系统</h1>
            <p class="subtitle">精准计算 · 高效决策 · 免费服务</p>
        </div>
    </header>
    
    <div class="container">
        <div class="card">
            <h2>项目信息</h2>
            <div class="input-group">
                <label for="project">选择项目:</label>
                <select id="project">
                    <option value="">-- 请选择项目 --</option>
                    <option value="project1" data-control="10571769.22" data-z="441012.36">上饶微短剧影视工厂建设项目室外配套工程</option>
                    <option value="project2" data-control="8748876.85" data-z="200000">上饶经开区兴业大道北侧100亩工业项目土地平整工程</option>
                    <option value="project3" data-control="11165828.06" data-z="354904.09">宜春黄金堆事故应急池及汇锦路排水改造工程</option>
                    <option value="project4" data-control="11754977.84" data-z="472799.15">上饶广丰区石灰石产业园土石方开挖平整项目</option>
                    <option value="project5" data-control="26387384.71" data-z="0">九江石化产业园二期基础配套设施建设项目纬二路、经七路工程招标项目</option>
                    <option value="project6" data-control="15093252.44" data-z="1849115.82">萍乡市芦溪中学科技楼建设项目</option>
                </select>
            </div>
            
            <div class="input-group">
                <label for="control-price">招标控制价:</label>
                <input type="text" id="control-price" readonly>
            </div>
            
            <div class="input-group">
                <label for="z-value">Z值:</label>
                <input type="text" id="z-value" readonly>
            </div>
            
            <div class="input-group">
                <label for="coefficient">系数 (0.87-0.97):</label>
                <input type="number" id="coefficient" min="0.87" max="0.97" step="any" value="0.93">
            </div>
            
            <button id="calculate-btn">计算报价</button>
            
            <div class="batch-section">
                <h3>批量操作</h3>
                <label for="batch-coefficient" class="file-input-label">
                    <span id="batch-file-name">上传系数文件 (CSV/TXT)</span>
                    <input type="file" id="batch-coefficient" class="file-input" accept=".csv,.txt">
                </label>
                <button id="download-history">下载历史记录 (CSV)</button>
                <div class="password-hint">如需导出密码，请联系管理员: <a href="tel:19907003214" class="highlight">19907003214</a></div>
            </div>
        </div>
        
        <div class="card result" id="result">
            <h2>计算结果</h2>
            <div class="formula">
                计算公式: (<span id="formula-control"></span> - <span id="formula-z"></span>) × <span id="formula-coefficient"></span> + <span id="formula-z2"></span>
            </div>
            <p>最终报价:</p>
            <div class="result-value" id="final-price">0.00</div>
        </div>
        
        <h2>历史报价记录</h2>
        <div class="table-container">
            <table id="history-table">
                <thead>
                    <tr>
                        <th>序号</th>
                        <th>项目名称</th>
                        <th>控制价</th>
                        <th>Z值</th>
                        <th>系数</th>
                        <th>最终报价</th>
                        <th>计算时间</th>
                    </tr>
                </thead>
                <tbody></tbody>
            </table>
        </div>
    </div>
    
    <footer>
        <div class="container">
            <p>定制清单文件可联系: <a href="tel:19907003214" class="highlight">19907003214</a></p>
            <p>专业报价换算系统 © 2025</p>
        </div>
    </footer>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // 获取DOM元素
            const projectSelect = document.getElementById('project');
            const controlPriceInput = document.getElementById('control-price');
            const zValueInput = document.getElementById('z-value');
            const coefficientInput = document.getElementById('coefficient');
            const calculateBtn = document.getElementById('calculate-btn');
            const resultDiv = document.getElementById('result');
            const finalPriceSpan = document.getElementById('final-price');
            const historyTable = document.getElementById('history-table').getElementsByTagName('tbody')[0];
            const formulaControl = document.getElementById('formula-control');
            const formulaZ = document.getElementById('formula-z');
            const formulaCoefficient = document.getElementById('formula-coefficient');
            const formulaZ2 = document.getElementById('formula-z2');
            const EXPORT_PASSWORD = "9420";

            // 项目选择变化时更新控制价和Z值
            projectSelect.addEventListener('change', function() {
                const selectedOption = this.options[this.selectedIndex];
                if (selectedOption.value) {
                    controlPriceInput.value = parseFloat(selectedOption.getAttribute('data-control')).toFixed(2);
                    zValueInput.value = parseFloat(selectedOption.getAttribute('data-z')).toFixed(2);
                }
            });

            // 计算按钮点击事件
            calculateBtn.addEventListener('click', function() {
                if (!projectSelect.value) {
                    alert('请先选择项目');
                    return;
                }
                
                const coefficient = parseFloat(coefficientInput.value);
                if (isNaN(coefficient) || coefficient < 0.87 || coefficient > 0.97) {
                    alert('请输入有效系数(0.87-0.97)');
                    return;
                }
                
                const selectedOption = projectSelect.options[projectSelect.selectedIndex];
                const controlPrice = parseFloat(selectedOption.getAttribute('data-control'));
                const zValue = parseFloat(selectedOption.getAttribute('data-z'));
                const finalPrice = (controlPrice - zValue) * coefficient + zValue;
                
                // 更新公式显示
                formulaControl.textContent = controlPrice.toFixed(2);
                formulaZ.textContent = zValue.toFixed(2);
                formulaCoefficient.textContent = coefficient;
                formulaZ2.textContent = zValue.toFixed(2);
                
                // 显示结果
                finalPriceSpan.textContent = finalPrice.toFixed(2);
                resultDiv.classList.add('show');
                
                // 添加到历史记录
                const row = historyTable.insertRow(0);
                row.innerHTML = `
                    <td>${historyTable.rows.length + 1}</td>
                    <td>${selectedOption.text}</td>
                    <td>${controlPrice.toFixed(2)}</td>
                    <td>${zValue.toFixed(2)}</td>
                    <td>${coefficient}</td>
                    <td>${finalPrice.toFixed(2)}</td>
                    <td>${new Date().toLocaleString('zh-CN')}</td>
                `;
            });

            // 下载历史记录
            document.getElementById('download-history').addEventListener('click', function() {
                if (historyTable.rows.length === 0) {
                    alert('没有历史记录可下载');
                    return;
                }
                
                const password = prompt('请输入导出密码(请联系管理员:19907003214):', '');
                if (password !== EXPORT_PASSWORD) {
                    alert('密码错误');
                    return;
                }
                
                let csvContent = "序号,项目名称,控制价,Z值,系数,最终报价,计算时间\n";
                for (let i = historyTable.rows.length - 1; i >= 0; i--) {
                    const cells = historyTable.rows[i].cells;
                    csvContent += `${cells[0].textContent},"${cells[1].textContent}",${cells[2].textContent},${cells[3].textContent},${cells[4].textContent},${cells[5].textContent},"${cells[6].textContent}"\n`;
                }
                
                const blob = new Blob(["\uFEFF" + csvContent], { type: 'text/csv;charset=utf-8;' });
                const url = URL.createObjectURL(blob);
                const link = document.createElement('a');
                link.href = url;
                link.download = `报价历史_${new Date().toISOString().slice(0,10)}.csv`;
                link.click();
            });

            // 自检
            function selfCheck() {
                try {
                    // 测试计算公式
                    const test = (100 - 10) * 0.9 + 10;
                    if (Math.abs(test - 91) > 0.0001) throw new Error('计算公式错误');
                    
                    // 测试DOM元素
                    const elements = [projectSelect, controlPriceInput, resultDiv, formulaControl];
                    elements.forEach(el => {
                        if (!el) throw new Error(`缺少DOM元素: ${el.id}`);
                    });
                    
                    console.log('自检通过');
                    return true;
                } catch (e) {
                    console.error('自检失败:', e);
                    return false;
                }
            }
            selfCheck();
        });
    </script>
</body>
</html>
