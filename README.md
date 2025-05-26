# 专业报价换算系统
<江西省专业工作室>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>专业报价换算系统</title>
    <style>
        :root {
            --primary-color: #3a7ca5;
            --secondary-color: #81c3d7;
            --accent-color: #2f6690;
            --dark-color: #16425b;
            --light-color: #e8f1f2;
            --success-color: #4caf50;
            --warning-color: #ff9800;
            --card-bg: rgba(255, 255, 255, 0.1);
            --border-color: rgba(255, 255, 255, 0.2);
            --glass-effect: blur(10px);
            --grid-color: rgba(129, 195, 215, 0.1);
            --text-shadow: 0 1px 3px rgba(0, 0, 0, 0.3);
            --card-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            --transition-duration: 0.3s;
        }

        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            scroll-behavior: smooth;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            background-color: var(--dark-color);
            color: var(--light-color);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
            background-image:
                radial-gradient(circle at 10% 20%, rgba(47, 102, 144, 0.2) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(58, 124, 165, 0.2) 0%, transparent 20%);
            background-attachment: fixed;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image:
                linear-gradient(var(--grid-color) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-color) 1px, transparent 1px);
            background-size: 30px 30px;
            z-index: -1;
            opacity: 0.5;
            animation: gridMove 60s linear infinite;
        }

        @keyframes gridMove {
            0% {
                background-position: 0 0;
            }

            100% {
                background-position: 300px 300px;
            }
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: clamp(15px, 3vw, 30px);
            position: relative;
        }

        header {
            text-align: center;
            padding: clamp(25px, 5vw, 40px) 0;
            background: linear-gradient(135deg, var(--primary-color), var(--dark-color));
            border-bottom: 1px solid var(--border-color);
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
            perspective: 1000px;
            margin-bottom: clamp(20px, 4vw, 40px);
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100" fill="none"><path d="M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z" fill="rgba(255,255,255,0.05)"/></svg>');
            opacity: 0.2;
            z-index: 0;
            animation: backgroundMove 30s linear infinite;
        }

        @keyframes backgroundMove {
            0% {
                transform: translate(0, 0);
            }

            100% {
                transform: translate(-50px, -50px);
            }
        }

        h1 {
            font-size: clamp(1.5rem, 4vw, 2.5rem);
            margin: 0;
            color: white;
            font-weight: 400;
            position: relative;
            z-index: 1;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 1s ease forwards 0.3s;
            text-shadow: var(--text-shadow);
        }

        .subtitle {
            font-size: clamp(0.8rem, 2vw, 1.1rem);
            color: var(--secondary-color);
            opacity: 0;
            margin-top: 8px;
            position: relative;
            z-index: 1;
            transform: translateY(20px);
            animation: fadeInUp 1s ease forwards 0.6s;
            text-shadow: var(--text-shadow);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h2 {
            color: white;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 8px;
            margin-top: 25px;
            font-size: clamp(1.2rem, 3vw, 1.7rem);
            font-weight: 400;
            display: flex;
            align-items: center;
            opacity: 0;
            transform: translateY(10px);
            animation: fadeInUp 0.8s ease forwards;
            text-shadow: var(--text-shadow);
        }

        h2::before {
            content: '•';
            color: var(--secondary-color);
            margin-right: 10px;
            font-size: 1.5em;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: clamp(15px, 3vw, 30px);
            margin-bottom: clamp(15px, 3vw, 30px);
            backdrop-filter: var(--glass-effect);
            transition: all var(--transition-duration) ease;
            position: relative;
            overflow: hidden;
            opacity: 0;
            transform: translateY(15px);
            animation: fadeInUp 0.8s ease forwards;
            box-shadow: var(--card-shadow);
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            transition: all 0.6s ease;
        }

        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
            border-color: rgba(129, 195, 215, 0.5);
        }

        .card:hover::before {
            left: 100%;
        }

        .card:nth-child(1) {
            animation-delay: 0.2s;
        }

        .card:nth-child(2) {
            animation-delay: 0.4s;
        }

        .card:nth-child(3) {
            animation-delay: 0.6s;
        }

        select,
        input,
        button,
        .file-input-label {
            width: 100%;
            background-color: rgba(255, 255, 255, 0.08);
            color: white;
            border: 1px solid var(--border-color);
            padding: clamp(12px, 3vw, 18px);
            margin: clamp(10px, 2vw, 15px) 0;
            border-radius: 8px;
            font-size: clamp(0.9rem, 2vw, 1.1rem);
            -webkit-appearance: none;
            transition: all var(--transition-duration) ease;
            position: relative;
        }

        select:focus,
        input:focus,
        button:focus,
        .file-input-label:focus {
            outline: none;
            box-shadow: 0 0 0 2px rgba(129, 195, 215, 0.5);
            border-color: var(--secondary-color);
        }

        select {
            background-image: url('data:image/svg+xml;utf8,<svg fill="%2381c3d7" height="24" viewBox="0 0 24 24" width="24" xmlns="http://www.w3.org/2000/svg"><path d="M7 10l5 5 5-5z"/></svg>');
            background-repeat: no-repeat;
            background-position: right 15px center;
            cursor: pointer;
        }

        select option {
            padding: 12px 15px;
            background-color: var(--dark-color);
            color: white;
            border: none;
        }

        button,
        .file-input-label {
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            color: white;
            font-weight: 500;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            text-shadow: var(--text-shadow);
            min-height: 50px;
        }

        button:hover,
        .file-input-label:hover {
            background: linear-gradient(135deg, var(--accent-color), var(--primary-color));
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        button:active,
        .file-input-label:active {
            transform: translateY(0);
            box-shadow: none;
        }

        button::before,
        .file-input-label::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: all 0.6s ease;
        }

        button:hover::before,
        .file-input-label:hover::before {
            left: 100%;
        }

        .result {
            display: none;
            animation: fadeIn var(--transition-duration) ease forwards;
        }

        .result.show {
            display: block;
        }

        .result-value {
            font-size: clamp(1.5rem, 4vw, 2.5rem);
            color: white;
            font-weight: 500;
            margin: clamp(15px, 3vw, 30px) 0;
            text-align: center;
            background: rgba(255, 255, 255, 0.08);
            padding: clamp(15px, 3vw, 30px);
            border-radius: 12px;
            border-left: 6px solid var(--secondary-color);
            transition: all var(--transition-duration) ease;
            position: relative;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            text-shadow: var(--text-shadow);
        }

        .result-value::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            transition: all 0.6s ease;
        }

        .result-value:hover {
            transform: scale(1.02);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
        }

        .result-value:hover::before {
            left: 100%;
        }

        .table-container {
            width: 100%;
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
            margin: clamp(15px, 3vw, 30px) 0;
            border-radius: 10px;
            border: 1px solid var(--border-color);
            position: relative;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: var(--glass-effect);
            box-shadow: var(--card-shadow);
        }

        .desktop-table {
            display: table;
        }

        .mobile-table {
            display: none;
        }

        @media (max-width: 767px) {
            .desktop-table {
                display: none;
            }

            .mobile-table {
                display: block;
            }

            .mobile-table .record {
                border: 1px solid var(--border-color);
                border-radius: 10px;
                margin-bottom: 15px;
                padding: 15px;
                background: rgba(255, 255, 255, 0.03);
                transition: all var(--transition-duration) ease;
                position: relative;
                overflow: hidden;
                box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            }

            .mobile-table .record::before {
                content: '';
                position: absolute;
                top: 0;
                left: -100%;
                width: 100%;
                height: 100%;
                background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.02), transparent);
                transition: all 0.6s ease;
            }

            .mobile-table .record:hover::before {
                left: 100%;
            }

            .mobile-table .record-header {
                display: flex;
                justify-content: space-between;
                align-items: center;
                margin-bottom: 15px;
                padding-bottom: 15px;
                border-bottom: 1px solid var(--border-color);
            }

            .mobile-table .record-id {
                font-weight: bold;
                color: var(--secondary-color);
                font-size: 1.1rem;
                text-shadow: var(--text-shadow);
            }

            .mobile-table .record-details {
                display: grid;
                grid-template-columns: 1fr 1fr;
                gap: 15px;
            }

            .mobile-table .detail-item {
                padding: 8px;
                border-radius: 6px;
                background: rgba(255, 255, 255, 0.03);
                transition: all var(--transition-duration) ease;
            }

            .mobile-table .detail-item:hover {
                background: rgba(255, 255, 255, 0.05);
            }

            .mobile-table .detail-label {
                font-size: 0.9rem;
                color: var(--secondary-color);
                margin-bottom: 3px;
                text-shadow: var(--text-shadow);
            }

            .mobile-table .delete-btn {
                margin-top: 15px;
            }
        }

        th,
        td {
            border: 1px solid var(--border-color);
            padding: clamp(8px, 2vw, 15px);
            text-align: left;
            font-size: clamp(0.85rem, 2vw, 1rem);
            transition: all var(--transition-duration) ease;
        }

        th {
            background-color: var(--primary-color);
            color: white;
            font-weight: 500;
            position: sticky;
            top: 0;
            z-index: 10;
            text-shadow: var(--text-shadow);
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        tbody tr:nth-child(even) {
            background-color: rgba(255, 255, 255, 0.05);
        }

        tbody tr:hover {
            background-color: rgba(255, 255, 255, 0.1);
            transform: translateX(2px);
            transition: all var(--transition-duration) ease;
        }

        /* 优化历史报价记录的UI显示 */
        #history-table th {
            background-color: var(--accent-color);
        }

        #history-table td {
            color: var(--light-color);
        }

        #history-table tr:nth-child(odd) {
            background-color: rgba(255, 255, 255, 0.02);
        }

        #history-table tr:hover {
            background-color: rgba(129, 195, 215, 0.1);
        }

        footer {
            text-align: center;
            padding: clamp(20px, 4vw, 40px) 0;
            margin-top: clamp(20px, 4vw, 50px);
            border-top: 1px solid var(--border-color);
            font-size: clamp(0.75rem, 2vw, 0.9rem);
            color: var(--secondary-color);
            background: linear-gradient(to top, rgba(22, 66, 91, 0.5), transparent);
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 1s ease forwards 0.8s;
            text-shadow: var(--text-shadow);
        }

        .formula {
            background-color: rgba(58, 124, 165, 0.1);
            padding: clamp(10px, 2vw, 20px);
            border-left: 4px solid var(--secondary-color);
            margin: clamp(15px, 3vw, 25px) 0;
            font-family: 'Courier New', monospace;
            border-radius: 8px;
            font-size: clamp(0.9rem, 2vw, 1.1rem);
            overflow-x: auto;
            position: relative;
            transition: all var(--transition-duration) ease;
            opacity: 0;
            transform: translateY(10px);
            animation: fadeInUp 0.8s ease forwards 0.5s;
            text-shadow: var(--text-shadow);
        }

        .formula:hover {
            background-color: rgba(58, 124, 165, 0.15);
        }

        .password-hint {
            margin-top: clamp(10px, 2vw, 20px);
            font-size: clamp(0.75rem, 2vw, 0.9rem);
            color: var(--secondary-color);
            text-align: center;
            line-height: 1.6;
            background: rgba(255, 255, 255, 0.03);
            padding: 10px 15px;
            border-radius: 8px;
            text-shadow: var(--text-shadow);
        }

        .highlight {
            color: var(--secondary-color);
            font-weight: 500;
            text-decoration: none;
            position: relative;
            transition: all var(--transition-duration) ease;
        }

        .highlight:hover {
            color: white;
        }

        .highlight:hover::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -2px;
            width: 100%;
            height: 2px;
            background-color: var(--secondary-color);
            animation: underline 0.3s ease forwards;
        }

        .delete-btn {
            background: linear-gradient(135deg, #e53935, #b71c1c);
            color: white;
            border: none;
            padding: clamp(6px, 1.5vw, 10px) clamp(10px, 2vw, 15px);
            border-radius: 6px;
            cursor: pointer;
            font-size: clamp(0.8rem, 1.5vw, 0.9rem);
            margin: 0 auto;
            display: block;
            transition: all var(--transition-duration) ease;
            position: relative;
            overflow: hidden;
            text-shadow: var(--text-shadow);
        }

        .delete-btn:hover {
            background: linear-gradient(135deg, #b71c1c, #e53935);
            transform: translateY(-2px);
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
        }

        .delete-btn:active {
            transform: translateY(0);
        }

        .delete-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: all 0.6s ease;
        }

        .delete-btn:hover::before {
            left: 100%;
        }

        .batch-results table {
            margin-top: 15px;
        }

        .batch-results th,
        .batch-results td {
            padding: 10px 15px;
        }

        #toast {
            position: fixed;
            bottom: clamp(20px, 4vw, 40px);
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            padding: clamp(10px, 2vw, 20px) clamp(15px, 3vw, 30px);
            border-radius: 10px;
            z-index: 100;
            font-size: clamp(0.85rem, 2vw, 1rem);
            opacity: 0;
            transition: opacity var(--transition-duration) ease, transform var(--transition-duration) ease;
            max-width: 80%;
            text-align: center;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            backdrop-filter: var(--glass-effect);
            text-shadow: var(--text-shadow);
        }

        #toast.show {
            opacity: 1;
            transform: translateX(-50%) translateY(-10px);
        }

        .loader {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s linear infinite;
            margin-right: 10px;
        }

        #calculating-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(22, 66, 91, 0.95);
            z-index: 1000;
            display: none;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            backdrop-filter: blur(15px);
        }

        #calculating-overlay.active {
            display: flex;
        }

        .calculating-title {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            color: white;
            margin-bottom: 30px;
            text-align: center;
            text-shadow: var(--text-shadow);
            position: relative;
        }

        .calculating-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 2px;
            background-color: var(--secondary-color);
        }

        .calculating-animation {
            position: relative;
            width: 120px;
            height: 120px;
            margin-bottom: 25px;
        }

        .calculating-circle {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 3px solid transparent;
            border-top-color: var(--secondary-color);
            animation: spin 1.5s linear infinite;
            box-shadow: 0 0 15px rgba(129, 195, 215, 0.2);
        }

        .calculating-circle:nth-child(2) {
            width: 80px;
            height: 80px;
            top: 20px;
            left: 20px;
            border-top-color: var(--primary-color);
            animation: spin 2s linear reverse infinite;
            box-shadow: 0 0 10px rgba(58, 124, 165, 0.2);
        }

        .calculating-circle:nth-child(3) {
            width: 40px;
            height: 40px;
            top: 40px;
            left: 40px;
            border-top-color: var(--accent-color);
            animation: spin 1s linear infinite;
            box-shadow: 0 0 5px rgba(47, 102, 144, 0.2);
        }

        .calculating-text {
            margin-top: 25px;
            font-size: clamp(1.1rem, 2vw, 1.3rem);
            color: var(--secondary-color);
            text-shadow: var(--text-shadow);
        }

        .calculating-numbers {
            display: flex;
            justify-content: center;
            margin-top: 15px;
        }

        .calculating-number {
            width: 30px;
            height: 30px;
            background: rgba(129, 195, 215, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 5px;
            font-size: 1.1rem;
            color: white;
            opacity: 0;
            animation: fadeInNumber 3s ease forwards;
            text-shadow: var(--text-shadow);
            box-shadow: 0 0 5px rgba(129, 195, 215, 0.3);
        }

        .calculating-number:nth-child(1) {
            animation-delay: 0s;
        }

        .calculating-number:nth-child(2) {
            animation-delay: 1s;
        }

        .calculating-number:nth-child(3) {
            animation-delay: 2s;
        }

        @keyframes spin {
            0% {
                transform: rotate(0deg);
            }

            100% {
                transform: rotate(360deg);
            }
        }

        @keyframes fadeInNumber {
            0% {
                opacity: 0;
                transform: scale(0.5);
            }

            20% {
                opacity: 1;
                transform: scale(1);
            }

            80% {
                opacity: 1;
                transform: scale(1);
            }

            100% {
                opacity: 0;
                transform: scale(0.5);
            }
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(129, 195, 215, 0.4);
            }

            70% {
                transform: scale(1.02);
                box-shadow: 0 0 0 10px rgba(129, 195, 215, 0);
            }

            100% {
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(129, 195, 215, 0);
            }
        }

        .pulse {
            animation: pulse 1.5s infinite;
        }

        .highlight-selection {
            box-shadow: 0 0 0 3px rgba(129, 195, 215, 0.5);
        }

        @keyframes underline {
            from {
                width: 0;
            }

            to {
                width: 100%;
            }
        }

        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }

        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb {
            background: rgba(129, 195, 215, 0.3);
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: rgba(129, 195, 215, 0.5);
        }

        .single-result {
            margin-top: 20px;
            padding: 15px;
            background: rgba(129, 195, 215, 0.1);
            border-radius: 8px;
            border-left: 4px solid var(--secondary-color);
            display: none;
            opacity: 0;
            transform: translateY(10px);
            transition: all var(--transition-duration) ease;
        }

        .single-result.show {
            display: block;
            animation: fadeInUp 0.5s ease forwards;
        }

        .single-result .result-item {
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 8px 12px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 6px;
            transition: all var(--transition-duration) ease;
        }

        .single-result .result-item:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateX(2px);
        }

        .single-result .result-label {
            color: var(--secondary-color);
            font-weight: 500;
            text-shadow: var(--text-shadow);
        }

        .single-result .result-value {
            color: white;
            font-size: 1.1rem;
            text-shadow: var(--text-shadow);
        }

        .batch-section {
            margin-top: 25px;
            padding-top: 20px;
            border-top: 1px solid var(--border-color);
        }

        /* 新增：移动端键盘适配 */
        @media (max-width: 767px) {
            body.keyboard-open .container {
                padding-bottom: 250px;
            }
        }

        /* 新增：触摸反馈效果 */
        select,
        input,
        button,
        .file-input-label,
        .delete-btn {
            -webkit-tap-highlight-color: rgba(129, 195, 215, 0.2);
        }

        /* 新增：表单元素聚焦状态 */
        select:focus,
        input:focus {
            transform: translateY(-2px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        /* 新增：页面进入动画 */
        .page-enter {
            opacity: 0;
            transform: translateY(20px);
        }

        .page-enter-active {
            opacity: 1;
            transform: translateY(0);
            transition: opacity 500ms, transform 500ms;
        }

        /* 新增：结果显示动画 */
        .result-enter {
            opacity: 0;
            transform: scale(0.95);
        }

        .result-enter-active {
            opacity: 1;
            transform: scale(1);
            transition: opacity 300ms, transform 300ms;
        }

        /* 新增：按钮点击波纹效果 */
        .ripple {
            position: absolute;
            border-radius: 50%;
            transform: scale(0);
            animation: ripple 600ms linear;
            background-color: rgba(255, 255, 255, 0.3);
        }

        @keyframes ripple {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }

        /* 新增：计算报价按钮提示 */
        .calculate-hint {
            text-align: center;
            margin-top: 5px;
            font-size: 0.9rem;
            color: var(--secondary-color);
        }

        .calculate-hint .wechat {
            color: var(--secondary-color);
            cursor: pointer;
            text-decoration: underline;
        }
    </style>
</head>

<body>
    <div class="toast" id="toast"></div>
    <div id="calculating-overlay">
        <div class="calculating-title">正在进行精密计算</div>
        <div class="calculating-animation">
            <div class="calculating-circle"></div>
            <div class="calculating-circle"></div>
            <div class="calculating-circle"></div>
        </div>
        <div class="calculating-text">请稍候...</div>
        <div class="calculating-numbers">
            <div class="calculating-number" id="count-3">3</div>
            <div class="calculating-number" id="count-2">2</div>
            <div class="calculating-number" id="count-1">1</div>
        </div>
    </div>

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
                    <option value="">-- 5.27开标项目 --</option>
                    <option value="project1" data-control="60271982.91" data-z="4604933.97">5.27-万安县枧头镇小微产业园标准厂房建设项目(一期)一标段</option>
                    <option value="project2" data-control="9037108.55" data-z="870755.2">5.27-横峰三中宿舍楼建设项目</option>
                    <option value="project3" data-control="2254316.76" data-z="94883.13">5.27-新干县中山路小区及温馨片区老旧小区改造项目</option>
                    <option value="project4" data-control="暂无" data-z="暂无">5.27-南昌经开区曰修路更新改造工程</option>
                    <option value="project5" data-control="4124563.18" data-z="0">5.27-2025年崇义县城区市政基础设施维修工程</option>
                    <option value="project6" data-control="64160060.35" data-z="2677000">5.27大余县再生水利用配置试点项目</option>
                    <option value="">-- 5.28开标项目 --</option>
                    <option value="project1" data-control="113659911.86" data-z="353241.46">5.28-鄱阳投资发展集团有限公司金源粮库高标准粮仓建设项目</option>
                    <option value="project2" data-control="2163313.96" data-z="91191.9">5.28-新干县城北润清花园小区及长运宿舍片区老旧小区改造项目</option>
                    <option value="project3" data-control="30796750.79" data-z="1208803.26">5.28-上饶微短剧影视工厂建设项目5#、6#、7#、8#、9#、10#、12#楼外立面改造工程</option>
                    <option value="project4" data-control="40851784.96" data-z="3310000">5.28-湖口县农业产业融合发展示范园建设项目</option>
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

            <button id="calculate-btn">
                <span class="loader"></span>
                <span>计算报价</span>
            </button>
            <!-- 新增：计算报价提示 -->
            <div class="calculate-hint">
                如需组价请添加微信 <span class="wechat" id="wechat-number">19907003214</span>
            </div>

            <!-- 单次计算结果显示区域 -->
            <div class="single-result" id="single-result">
                <h3>单次计算结果</h3>
                <div class="result-item">
                    <div class="result-label">项目名称:</div>
                    <div class="result-value" id="single-project-name">-</div>
                </div>
                <div class="result-item">
                    <div class="result-label">控制价:</div>
                    <div class="result-value" id="single-control-price">-</div>
                </div>
                <div class="result-item">
                    <div class="result-label">Z值:</div>
                    <div class="result-value" id="single-z-value">-</div>
                </div>
                <div class="result-item">
                    <div class="result-label">系数:</div>
                    <div class="result-value" id="single-coefficient">-</div>
                </div>
                <div class="result-item pulse">
                    <div class="result-label">最终报价:</div>
                    <div class="result-value" id="single-final-price">-</div>
                </div>
            </div>

            <div class="batch-section">
                <h3>批量操作</h3>
                <label for="batch-coefficient" class="file-input-label">
                    <span id="batch-file-name">上传系数文件 (CSV/TXT)</span>
                </label>
                <input type="file" id="batch-coefficient" class="file-input" accept=".csv,.txt" style="display: none;">
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
            <!-- 桌面端表格 -->
            <table id="history-table" class="desktop-table">
                <thead>
                    <tr>
                        <th>序号</th>
                        <th>项目名称</th>
                        <th>控制价</th>
                        <th>Z值</th>
                        <th>系数</th>
                        <th>最终报价</th>
                        <th>计算时间</th>
                        <th>操作</th>
                    </tr>
                </thead>
                <tbody></tbody>
            </table>

            <!-- 移动端表格 -->
            <div id="mobile-history" class="mobile-table"></div>
        </div>
    </div>

    <footer>
        <div class="container">
            <p>定制清单文件可联系: <a href="tel:19907003214" class="highlight">19907003214</a></p>
            <p>专业报价换算系统 © 2025</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            // 获取DOM元素
            const projectSelect = document.getElementById('project');
            const controlPriceInput = document.getElementById('control-price');
            const zValueInput = document.getElementById('z-value');
            const coefficientInput = document.getElementById('coefficient');
            const calculateBtn = document.getElementById('calculate-btn');
            const singleResult = document.getElementById('single-result');
            const singleProjectName = document.getElementById('single-project-name');
            const singleControlPrice = document.getElementById('single-control-price');
            const singleZValue = document.getElementById('single-z-value');
            const singleCoefficient = document.getElementById('single-coefficient');
            const singleFinalPrice = document.getElementById('single-final-price');
            const result = document.getElementById('result');
            const finalPrice = document.getElementById('final-price');
            const formulaControl = document.getElementById('formula-control');
            const formulaZ = document.getElementById('formula-z');
            const formulaCoefficient = document.getElementById('formula-coefficient');
            const formulaZ2 = document.getElementById('formula-z2');
            const historyTable = document.getElementById('history-table').getElementsByTagName('tbody')[0];
            const mobileHistory = document.getElementById('mobile-history');
            const toast = document.getElementById('toast');
            const calculatingOverlay = document.getElementById('calculating-overlay');
            const wechatNumber = document.getElementById('wechat-number');

            // 微信点击事件
            wechatNumber.addEventListener('click', function () {
                const text = this.textContent;
                const textarea = document.createElement('textarea');
                textarea.value = text;
                document.body.appendChild(textarea);
                textarea.select();
                document.execCommand('copy');
                document.body.removeChild(textarea);
                showToast('微信账号已复制');
                window.location.href = `weixin://`;
            });

            // 显示提示信息
            function showToast(message) {
                toast.textContent = message;
                toast.classList.add('show');
                setTimeout(() => {
                    toast.classList.remove('show');
                }, 3000);
            }

            // 项目选择事件
            projectSelect.addEventListener('change', function () {
                const selectedOption = this.options[this.selectedIndex];
                controlPriceInput.value = selectedOption.getAttribute('data-control');
                zValueInput.value = selectedOption.getAttribute('data-z');
            });

            // 计算报价事件
            calculateBtn.addEventListener('click', function () {
                const selectedOption = projectSelect.options[projectSelect.selectedIndex];
                if (selectedOption.value === '') {
                    showToast('请选择项目');
                    return;
                }
                const controlPrice = parseFloat(controlPriceInput.value);
                const zValue = parseFloat(zValueInput.value);
                const coefficient = parseFloat(coefficientInput.value);

                if (isNaN(controlPrice) || isNaN(zValue) || isNaN(coefficient)) {
                    showToast('输入值无效');
                    return;
                }

                calculatingOverlay.classList.add('active');
                setTimeout(() => {
                    calculatingOverlay.classList.remove('active');
                    const final = (controlPrice - zValue) * coefficient + zValue;

                    // 显示单次计算结果
                    singleProjectName.textContent = selectedOption.text;
                    singleControlPrice.textContent = controlPrice;
                    singleZValue.textContent = zValue;
                    singleCoefficient.textContent = coefficient;
                    singleFinalPrice.textContent = final;
                    singleResult.classList.add('show');

                    // 显示计算结果
                    formulaControl.textContent = controlPrice;
                    formulaZ.textContent = zValue;
                    formulaCoefficient.textContent = coefficient;
                    formulaZ2.textContent = zValue;
                    finalPrice.textContent = final;
                    result.classList.add('show');

                    // 添加历史记录
                    const now = new Date();
                    const time = now.toLocaleString();
                    const newRow = historyTable.insertRow();
                    const cells = [
                        historyTable.rows.length,
                        selectedOption.text,
                        controlPrice,
                        zValue,
                        coefficient,
                        final,
                        time,
                        '<button class="delete-btn">删除</button>'
                    ];
                    cells.forEach((cellText, index) => {
                        const cell = newRow.insertCell(index);
                        cell.textContent = cellText;
                    });

                    // 移动端历史记录
                    const record = document.createElement('div');
                    record.classList.add('record');
                    record.innerHTML = `
                        <div class="record-header">
                            <span class="record-id">记录 #${historyTable.rows.length}</span>
                            <button class="delete-btn">删除</button>
                        </div>
                        <div class="record-details">
                            <div class="detail-item">
                                <div class="detail-label">项目名称</div>
                                <div class="detail-value">${selectedOption.text}</div>
                            </div>
                            <div class="detail-item">
                                <div class="detail-label">控制价</div>
                                <div class="detail-value">${controlPrice}</div>
                            </div>
                            <div class="detail-item">
                                <div class="detail-label">Z值</div>
                                <div class="detail-value">${zValue}</div>
                            </div>
                            <div class="detail-item">
                                <div class="detail-label">系数</div>
                                <div class="detail-value">${coefficient}</div>
                            </div>
                            <div class="detail-item">
                                <div class="detail-label">最终报价</div>
                                <div class="detail-value">${final}</div>
                            </div>
                            <div class="detail-item">
                                <div class="detail-label">计算时间</div>
                                <div class="detail-value">${time}</div>
                            </div>
                        </div>
                    `;
                    mobileHistory.appendChild(record);

                    // 删除历史记录事件
                    const deleteBtns = document.querySelectorAll('.delete-btn');
                    deleteBtns.forEach(btn => {
                        btn.addEventListener('click', function () {
                            const row = this.closest('tr');
                            if (row) {
                                const index = row.rowIndex - 1;
                                historyTable.deleteRow(index);
                                mobileHistory.children[index].remove();
                                // 更新序号
                                Array.from(historyTable.rows).forEach((row, i) => {
                                    row.cells[0].textContent = i + 1;
                                });
                            }
                        });
                    });
                }, 2000);
            });
        });
    </script>
</body>

</html>
