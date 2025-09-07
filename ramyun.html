<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>라면 타이머</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.7.77/Tone.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+KR:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'IBM Plex Sans KR', sans-serif;
        }
        /* Gradient animation for the button */
        .animated-gradient {
            background-size: 200% auto;
            transition: background-position 0.5s ease-out;
        }
        .animated-gradient:hover {
            background-position: right center;
        }
    </style>
</head>
<body class="bg-gray-900 flex items-center justify-center min-h-screen">

    <div class="bg-gray-800 text-white w-full max-w-md mx-4 rounded-2xl shadow-2xl p-6 md:p-8 border border-gray-700 transform transition-all duration-500">
        
        <!-- Header -->
        <header class="text-center mb-6">
            <h1 class="text-3xl font-bold text-red-500">라면, 예술로 끓이다</h1>
            <p class="text-gray-400 mt-2">황금 레시피 라면 타이머</p>
        </header>

        <!-- Progress Bar -->
        <div class="w-full bg-gray-700 rounded-full h-2.5 mb-6">
            <div id="progress-bar" class="bg-red-500 h-2.5 rounded-full transition-all duration-500" style="width: 0%"></div>
        </div>

        <!-- Timer Display -->
        <div class="bg-gray-900 rounded-lg py-8 mb-6 flex justify-center items-center border border-gray-700">
            <span id="timer-display" class="text-7xl font-bold tracking-widest text-white">00:00</span>
        </div>
        
        <!-- Instructions -->
        <div id="instruction-card" class="bg-gray-700 rounded-lg p-5 mb-6 min-h-[120px] flex flex-col justify-center items-center text-center">
            <p id="instruction-text" class="text-lg font-medium text-gray-200"></p>
        </div>

        <!-- Control Button -->
        <button id="control-button" class="w-full py-4 text-lg font-bold text-white rounded-lg shadow-lg focus:outline-none focus:ring-4 focus:ring-red-500/50 bg-gradient-to-r from-red-500 to-orange-500 animated-gradient">
            요리 시작
        </button>
    </div>

    <script>
        const timerDisplay = document.getElementById('timer-display');
        const instructionText = document.getElementById('instruction-text');
        const controlButton = document.getElementById('control-button');
        const progressBar = document.getElementById('progress-bar');

        const steps = [
            {
                instruction: "세상에서 가장 맛있는 라면을 끓여볼까요?",
                buttonLabel: "요리 시작"
            },
            {
                instruction: "1. 냄비에 물 550ml를 붓고 끓여주세요.<br>물이 끓으면 아래 버튼을 눌러주세요.",
                buttonLabel: "물이 끓어요!"
            },
            {
                instruction: "2. 면, 분말스프, 후레이크를 모두 넣고<br>타이머 시작 버튼을 눌러주세요.",
                buttonLabel: "타이머 시작"
            },
            {
                instruction: "면을 익힙니다. (3분)",
                duration: 180, // 3 minutes
                buttonLabel: "초기화"
            },
            {
                instruction: "3. 계란을 깨뜨리지 않고 조심스럽게 넣어주세요.<br>(반숙을 위해 젓지 마세요!)",
                duration: 60, // 1 minute
                buttonLabel: "초기화"
            },
            {
                instruction: "4. 송송 썬 파를 넣고 잠시 더 끓입니다.",
                duration: 30, // 30 seconds
                buttonLabel: "초기화"
            },
            {
                instruction: "완성! 불을 끄고 반숙 계란과 함께 즐겨보세요!",
                buttonLabel: "다시 끓이기"
            }
        ];

        let currentStep = 0;
        let timerInterval = null;
        let timeLeft = 0;
        let synth;

        // 사운드 초기화
        function initializeAudio() {
            if (!synth) {
                synth = new Tone.Synth().toDestination();
                // 브라우저의 오디오 컨텍스트 활성화
                Tone.start(); 
            }
        }
        
        function updateUI() {
            const step = steps[currentStep];
            instructionText.innerHTML = step.instruction;
            controlButton.textContent = step.buttonLabel;
            
            const progressPercentage = (currentStep / (steps.length - 1)) * 100;
            progressBar.style.width = `${progressPercentage}%`;
        }

        function formatTime(seconds) {
            const minutes = Math.floor(seconds / 60);
            const remainingSeconds = seconds % 60;
            return `${String(minutes).padStart(2, '0')}:${String(remainingSeconds).padStart(2, '0')}`;
        }

        function playSound(note, duration) {
            if (synth) {
                synth.triggerAttackRelease(note, duration);
            }
        }

        function startTimer(duration) {
            timeLeft = duration;
            timerDisplay.textContent = formatTime(timeLeft);
            
            clearInterval(timerInterval); // 기존 타이머 정리
            timerInterval = setInterval(() => {
                timeLeft--;
                timerDisplay.textContent = formatTime(timeLeft);
                
                if (timeLeft < 0) {
                    clearInterval(timerInterval);
                    playSound("C5", "0.2");
                    currentStep++;
                    updateUI();

                    const nextStep = steps[currentStep];
                    if (nextStep.duration > 0) {
                        // 자동으로 다음 타이머 단계 시작
                        startTimer(nextStep.duration);
                    } else {
                        // 요리 끝, 완료 사운드 재생
                        setTimeout(() => playSound("G5", "0.2"), 200);
                        timerDisplay.textContent = "00:00";
                    }
                }
            }, 1000);
        }

        function handleButtonClick() {
            initializeAudio(); // 사용자가 상호작용할 때 오디오 컨텍스트 시작
            playSound("C4", "0.1");

            // 요리 중 (계란, 파 넣는 단계 포함) '초기화' 버튼을 누른 경우
            if (currentStep >= 3 && currentStep <= 5) {
                clearInterval(timerInterval);
                currentStep = 0;
                timeLeft = 0;
                timerDisplay.textContent = formatTime(0);
                updateUI();
                return;
            }

            currentStep++;
            if (currentStep >= steps.length) {
                currentStep = 0;
            }

            updateUI();

            const currentStepData = steps[currentStep];
            if (currentStepData && currentStepData.duration > 0) {
                startTimer(currentStepData.duration);
            } else {
                 clearInterval(timerInterval);
                 if(currentStep === 0) {
                    timerDisplay.textContent = formatTime(0);
                 }
            }
        }

        controlButton.addEventListener('click', handleButtonClick);

        // 초기 상태 설정
        window.onload = () => {
            updateUI();
            timerDisplay.textContent = formatTime(0);
        };
    </script>
</body>
</html>

