# lofi-study-room
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minhyuck's Lofi Study Room</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { background: #0f172a; color: white; font-family: 'Inter', sans-serif; }
        .glass { background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(10px); border: 1px solid rgba(255, 255, 255, 0.1); }
    </style>
</head>
<body class="p-4 md:p-8">
    <div class="flex justify-between items-center mb-8">
        <h1 class="text-2xl font-bold text-indigo-400">🌙 Lofi Study Room</h1>
        <div id="timer" class="glass px-6 py-2 rounded-full text-xl font-mono">25:00</div>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-4 gap-6">
        <div class="lg:col-span-3 aspect-video glass rounded-3xl overflow-hidden relative">
            <iframe src="https://your-room.daily.co/study-session" 
                    allow="camera; microphone; fullscreen" 
                    class="w-full h-full border-none"></iframe>
        </div>

        <div class="space-y-6">
            <div class="glass p-4 rounded-2xl">
                <h2 class="text-sm font-semibold mb-3 opacity-70">LIVE MUSIC</h2>
                <div class="aspect-video rounded-lg overflow-hidden mb-4">
                    <iframe width="100%" height="100%" src="https://www.youtube.com/embed/jfKfPfyJRdk?autoplay=1&mute=1" frameborder="0" allow="autoplay; encrypted-media"></iframe>
                </div>
                <p class="text-xs text-center opacity-50">Lofi Girl - Radio</p>
            </div>

            <div class="glass p-6 rounded-2xl">
                <h2 class="text-sm font-semibold mb-4 opacity-70">TIMER CONTROL</h2>
                <button onclick="startTimer()" class="w-full bg-indigo-600 hover:bg-indigo-500 py-3 rounded-xl font-bold transition">Start Focus</button>
            </div>
        </div>
    </div>

    <script>
        function startTimer() {
            let time = 25 * 60;
            const display = document.querySelector('#timer');
            setInterval(() => {
                let mins = parseInt(time / 60, 10);
                let secs = parseInt(time % 60, 10);
                display.textContent = `${mins < 10 ? "0" + mins : mins}:${secs < 10 ? "0" + secs : secs}`;
                if (--time < 0) time = 0;
            }, 1000);
        }
    </script>
</body>
</html>
