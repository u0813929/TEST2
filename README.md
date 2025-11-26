<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的個人網站 - 簡介與作品集</title>
    <!-- 載入 Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 使用 Inter 字體作為網頁字體 -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <!-- 導覽列 (Sticky Navigation) -->
    <header class="sticky top-0 z-50 bg-white/95 backdrop-blur-sm shadow-md">
        <nav class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <a href="#" class="text-xl font-bold text-indigo-600 hover:text-indigo-800 transition-colors">
                個人品牌
            </a>
            <div class="flex space-x-4">
                <a href="#about" class="text-gray-600 hover:text-indigo-600 font-medium transition-colors p-2 rounded-lg">關於我</a>
                <a href="#skills" class="text-gray-600 hover:text-indigo-600 font-medium transition-colors p-2 rounded-lg">技能與作品</a>
                <a href="#contact" class="text-gray-600 hover:text-indigo-600 font-medium transition-colors p-2 rounded-lg">聯繫我</a>
            </div>
        </nav>
    </header>

    <main class="max-w-4xl mx-auto p-4 sm:p-6 lg:p-8 space-y-16">

        <!-- Hero / 首頁橫幅區塊 -->
        <section id="hero" class="pt-10 pb-16 text-center">
            <div class="w-32 h-32 mx-auto mb-6">
                <!-- 頭像 Placeholder -->
                <img 
                    class="rounded-full w-full h-full object-cover shadow-xl border-4 border-white ring-4 ring-indigo-200"
                    src="https://placehold.co/300x300/6366f1/ffffff?text=Your+Photo" 
                    alt="個人頭像"
                    onerror="this.onerror=null; this.src='https://placehold.co/300x300/6366f1/ffffff?text=Your+Photo'"
                >
            </div>
            <h1 class="text-4xl font-extrabold text-gray-900 mb-2">
                你好，我是 [你的姓名]
            </h1>
            <p class="text-xl font-light text-indigo-600 mb-6">
                一位充滿熱情的 [你的職業/角色]
            </p>
            <p class="max-w-2xl mx-auto text-gray-600 leading-relaxed">
                我專注於將創意轉化為實際的解決方案，並在 [你的主要領域] 擁有豐富的經驗。歡迎探索我的作品和專長！
            </p>
        </section>
        
        <!-- 關於我區塊 -->
        <section id="about" class="bg-white p-8 rounded-3xl shadow-xl border border-gray-100">
            <h2 class="text-3xl font-bold text-gray-900 mb-6 border-b-2 border-indigo-200 pb-2 flex items-center gap-2">
                <!-- Icon: User -->
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-6 h-6 text-indigo-500"><path d="M19 21v-2a4 4 0 0 0-4-4H9a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                關於我
            </h2>
            <div class="space-y-4 text-gray-700">
                <p>
                    我在 [你的領域] 累積了 [X] 年的經驗，擅長 [主要技能 A] 和 [主要技能 B]。我的職業生涯一直致力於 [你的目標或核心價值]。
                </p>
                <p>
                    我相信持續學習的重要性。目前，我正在鑽研 [新技能或新技術]，希望將其應用於未來的專案中，創造出更具影響力的成果。
                </p>
            </div>
            <div class="mt-6">
                <a href="#contact" class="inline-block bg-indigo-600 text-white font-semibold py-3 px-6 rounded-xl hover:bg-indigo-700 transition-all shadow-lg hover:shadow-xl">
                    開始對話
                </a>
            </div>
        </section>

        <!-- 技能與作品集區塊 -->
        <section id="skills" class="space-y-8">
            <h2 class="text-3xl font-bold text-gray-900 mb-6 border-b-2 border-indigo-200 pb-2 flex items-center gap-2">
                <!-- Icon: Code -->
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-6 h-6 text-indigo-500"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
                核心技能
            </h2>

            <!-- 技能標籤 -->
            <div class="flex flex-wrap gap-3">
                <span class="px-4 py-2 bg-indigo-100 text-indigo-800 font-medium rounded-full shadow-md">JavaScript / TypeScript</span>
                <span class="px-4 py-2 bg-indigo-100 text-indigo-800 font-medium rounded-full shadow-md">React / Angular</span>
                <span class="px-4 py-2 bg-indigo-100 text-indigo-800 font-medium rounded-full shadow-md">Tailwind CSS</span>
                <span class="px-4 py-2 bg-indigo-100 text-indigo-800 font-medium rounded-full shadow-md">雲端運算 (GCP/AWS)</span>
            </div>

            <h3 class="text-2xl font-bold text-gray-900 mt-10 mb-6 border-b border-gray-200 pb-2">
                精選作品集
            </h3>

            <!-- 作品卡片 Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <!-- 作品 1 -->
                <div class="bg-white p-6 rounded-2xl shadow-lg hover:shadow-xl transition-shadow border border-gray-100">
                    <h4 class="text-xl font-bold text-indigo-600 mb-2">專案名稱 A：[主題]</h4>
                    <p class="text-gray-600 mb-4 text-sm">
                        這是關於一個 [簡短說明] 的專案。我的主要貢獻是 [你的貢獻]。
                    </p>
                    <a href="https://example.com" target="_blank" class="text-indigo-500 hover:text-indigo-700 font-medium transition-colors flex items-center gap-1">
                        查看專案連結 
                        <!-- Icon: Arrow Right -->
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
                    </a>
                </div>

                <!-- 作品 2 -->
                <div class="bg-white p-6 rounded-2xl shadow-lg hover:shadow-xl transition-shadow border border-gray-100">
                    <h4 class="text-xl font-bold text-indigo-600 mb-2">專案名稱 B：[主題]</h4>
                    <p class="text-gray-600 mb-4 text-sm">
                        此專案應用了 [技術名稱] 來解決 [問題]。成果是 [結果或效益]。
                    </p>
                    <a href="https://example.com" target="_blank" class="text-indigo-500 hover:text-indigo-700 font-medium transition-colors flex items-center gap-1">
                        查看專案連結 
                        <!-- Icon: Arrow Right -->
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
                    </a>
                </div>
            </div>
        </section>

        <!-- 聯繫我區塊 -->
        <section id="contact" class="bg-indigo-50 p-8 rounded-3xl shadow-inner border border-indigo-200">
            <h2 class="text-3xl font-bold text-gray-900 mb-6 border-b-2 border-indigo-300 pb-2 flex items-center gap-2">
                <!-- Icon: Mail -->
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-6 h-6 text-indigo-600"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                聯繫我
            </h2>
            <p class="text-gray-700 mb-6">
                如果您對我的作品感興趣，或有任何合作機會，歡迎隨時與我聯繫！
            </p>

            <div class="space-y-4">
                <!-- Email -->
                <div class="flex items-center gap-4 bg-white p-4 rounded-xl shadow-md">
                    <span class="text-indigo-600">
                        <!-- Icon: At Sign -->
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><circle cx="12" cy="12" r="4"/><path d="M16 8v5a3 3 0 0 0 6 0v-1a10 10 0 1 0-4 8"/></svg>
                    </span>
                    <div>
                        <p class="text-sm font-medium text-gray-500">電子郵件</p>
                        <a href="mailto:your.email@example.com" class="text-gray-800 hover:text-indigo-600 transition-colors font-semibold">
                            your.email@example.com
                        </a>
                    </div>
                </div>

                <!-- LinkedIn/其他社群媒體 -->
                <div class="flex items-center gap-4 bg-white p-4 rounded-xl shadow-md">
                    <span class="text-indigo-600">
                        <!-- Icon: Link -->
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>
                    </span>
                    <div>
                        <p class="text-sm font-medium text-gray-500">個人檔案連結 (例如 LinkedIn / GitHub)</p>
                        <a href="https://linkedin.com/in/yourname" target="_blank" class="text-gray-800 hover:text-indigo-600 transition-colors font-semibold">
                            /in/yourname
                        </a>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- 頁腳 -->
    <footer class="mt-16 border-t border-gray-200 py-6">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-sm text-gray-500">
            &copy; 2025 [你的姓名]. All rights reserved. | 簡約個人網站範本
        </div>
    </footer>

</body>
</html>
      </div>
    </div>
  );
}
