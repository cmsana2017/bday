<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Good Morning Sunrise</title>
    <style>
        body {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            height: 100%;
            font-family: 'Georgia', serif;
            overflow: hidden;
        }

        html {
            height: 100%;
        }

        .sunrise-container {
            position: relative;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, 
                #87CEEB 0%,
                #FFB6C1 30%,
                #FFA07A 60%,
                #FFD700 80%,
                #FFF8DC 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            animation: skyTransition 8s ease-in-out infinite alternate;
        }

        @keyframes skyTransition {
            0% {
                background: linear-gradient(to bottom, 
                    #191970 0%,
                    #4B0082 30%,
                    #8B008B 60%,
                    #FF4500 80%,
                    #FFD700 100%);
            }
            100% {
                background: linear-gradient(to bottom, 
                    #87CEEB 0%,
                    #FFB6C1 30%,
                    #FFA07A 60%,
                    #FFD700 80%,
                    #FFF8DC 100%);
            }
        }

        .sun {
            position: absolute;
            width: 120px;
            height: 120px;
            background: radial-gradient(circle, #FFD700 0%, #FFA500 70%, #FF8C00 100%);
            border-radius: 50%;
            top: 20%;
            right: 15%;
            box-shadow: 0 0 50px #FFD700, 0 0 100px #FFA500;
            animation: sunRise 8s ease-in-out infinite alternate;
        }

        @keyframes sunRise {
            0% {
                top: 70%;
                opacity: 0.3;
                transform: scale(0.8);
            }
            100% {
                top: 20%;
                opacity: 1;
                transform: scale(1);
            }
        }

        .clouds {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .cloud {
            position: absolute;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50px;
            opacity: 0.7;
            animation: float 15s ease-in-out infinite;
        }

        .cloud:before,
        .cloud:after {
            content: '';
            position: absolute;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50px;
        }

        .cloud1 {
            width: 80px;
            height: 40px;
            top: 25%;
            left: 10%;
            animation-delay: 0s;
        }

        .cloud1:before {
            width: 50px;
            height: 50px;
            top: -25px;
            left: 10px;
        }

        .cloud1:after {
            width: 60px;
            height: 40px;
            top: -15px;
            right: 10px;
        }

        .cloud2 {
            width: 60px;
            height: 30px;
            top: 15%;
            right: 25%;
            animation-delay: -5s;
        }

        .cloud2:before {
            width: 40px;
            height: 40px;
            top: -20px;
            left: 8px;
        }

        .cloud2:after {
            width: 50px;
            height: 30px;
            top: -10px;
            right: 8px;
        }

        @keyframes float {
            0%, 100% {
                transform: translateX(0px) translateY(0px);
            }
            50% {
                transform: translateX(20px) translateY(-10px);
            }
        }

        .message-container {
            text-align: center;
            z-index: 10;
            padding: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            animation: messageGlow 3s ease-in-out infinite alternate;
        }

        @keyframes messageGlow {
            0% {
                box-shadow: 0 8px 32px rgba(255, 215, 0, 0.2);
            }
            100% {
                box-shadow: 0 8px 32px rgba(255, 215, 0, 0.4);
            }
        }

        .good-morning {
            font-size: 3.5rem;
            font-weight: bold;
            color: #2C3E50;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(255, 255, 255, 0.5);
            animation: textShine 4s ease-in-out infinite;
        }

        @keyframes textShine {
            0%, 100% {
                color: #2C3E50;
            }
            50% {
                color: #E67E22;
            }
        }

        .subtitle {
            font-size: 1.5rem;
            color: #34495E;
            font-style: italic;
            margin-bottom: 15px;
            opacity: 0.9;
        }

        .bliss-text {
            font-size: 1.2rem;
            color: #7F8C8D;
            line-height: 1.6;
            max-width: 400px;
            margin: 0 auto;
        }

        .birds {
            position: absolute;
            top: 30%;
            left: 20%;
            font-size: 1.5rem;
            animation: flyAcross 12s linear infinite;
        }

        @keyframes flyAcross {
            0% {
                left: -10%;
                top: 30%;
            }
            50% {
                left: 50%;
                top: 25%;
            }
            100% {
                left: 110%;
                top: 35%;
            }
        }

        @media (max-width: 768px) {
            .good-morning {
                font-size: 2.5rem;
            }
            
            .subtitle {
                font-size: 1.2rem;
            }
            
            .bliss-text {
                font-size: 1rem;
            }
            
            .message-container {
                padding: 30px 20px;
                margin: 20px;
            }
            
            .sun {
                width: 80px;
                height: 80px;
            }
        }
    </style>
</head>
<body>
    <div class="sunrise-container">
        <div class="sun"></div>
        
        <div class="clouds">
            <div class="cloud cloud1"></div>
            <div class="cloud cloud2"></div>
        </div>
        
        <div class="birds">🕊️ 🕊️ 🕊️</div>
        
        <div class="message-container">
            <h1 class="good-morning">Good Morning!</h1>
            <p class="subtitle">Rise and Shine</p>
            <p class="bliss-text">
                Welcome this beautiful day filled with endless possibilities. 
                Let the warmth of the morning sun fill your heart with joy and peace.
            </p>
        </div>
    </div>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'990e7a3f4389ca8c',t:'MTc2MDg1ODA1NS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
