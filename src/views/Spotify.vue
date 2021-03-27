<template>
    <div class="flex h-screen">
        <!-- side menu -->
        <div class="w-1/5 bg-black p-3"> 
            <!-- logo -->
            <img src="../assets/spotify/logo.png" width="120" class="m-3"> 
            <!-- top menu -->
            <div class="py-14 m-2">
                <div class="flex py-3 hover:bg-gray-500 rounded-md"> 
                    <svg class="text-white" viewBox="0 0 512 512" width="24" height="24" xmlns="http://www.w3.org/2000/svg"><path d="M 256.274 60.84 L 84.324 166.237 L 84.324 443.063 L 193.27 443.063 L 193.27 293.73 L 320.228 293.73 L 320.228 443.063 L 428.222 443.063 L 428.222 165.476 L 256.274 60.84 Z M 256.274 35.95 L 448.452 149.145 L 448.452 464.395 L 300 464.395 L 300 315.062 L 213.499 315.062 L 213.499 464.395 L 64.095 464.395 L 64.095 150.161 L 256.274 35.95 Z" fill="currentColor"></path></svg>
                    <p class="text-white font-bold pl-2">Home</p>
                </div>
                <div class="flex py-3 hover:bg-gray-500 rounded-md">
                    <svg class="text-white" viewBox="0 0 512 512" width="24" height="24" xmlns="http://www.w3.org/2000/svg"><path d="M349.714 347.937l93.714 109.969-16.254 13.969-93.969-109.969q-48.508 36.825-109.207 36.825-36.826 0-70.476-14.349t-57.905-38.603-38.603-57.905-14.349-70.476 14.349-70.476 38.603-57.905 57.905-38.603 70.476-14.349 70.476 14.349 57.905 38.603 38.603 57.905 14.349 70.476q0 37.841-14.73 71.619t-40.889 58.921zM224 377.397q43.428 0 80.254-21.461t58.286-58.286 21.461-80.254-21.461-80.254-58.286-58.285-80.254-21.46-80.254 21.46-58.285 58.285-21.46 80.254 21.46 80.254 58.285 58.286 80.254 21.461z" fill="currentColor" fill-rule="evenodd"></path></svg>
                    <p class="text-white font-bold pl-2">検索</p>
                </div>
                <div class="flex py-3 hover:bg-gray-500 rounded-md">
                    <svg class="text-white" viewBox="0 0 512 512" width="24" height="24" xmlns="http://www.w3.org/2000/svg"><path d="M291.301 81.778l166.349 373.587-19.301 8.635-166.349-373.587zM64 463.746v-384h21.334v384h-21.334zM192 463.746v-384h21.334v384h-21.334z" fill="currentColor"></path></svg>
                    <p class="text-white font-bold pl-2">My Library</p>
                </div>
            </div>
            <!-- playlist menu --> 
            <div class="border-b-2 border-gray-400">
                <div class="flex my-3"> 
                    <img src="../assets/spotify/liked-songs-300.png" width="30">
                    <p class="text-gray-400 font-bold mx-3">プレイリストを作成</p>
                </div>
                <div class="flex my-3"> 
                    <img src="../assets/spotify/liked-songs-300.png" width="30">
                    <p class="text-gray-400 font-bold mx-3">お気に入りの曲</p>
                </div>
            </div>
        </div>
        <div class="w-4/5 bg-gradient-to-b from-purple-800 to-gray-900 py-2 px-4"> 
            <!-- account info menu -->
            <div class="flex justify-end"> 
                <div class="bg-black border rounded-3xl p-2 mx-5"> 
                    <p class="text-white font-bold text-sm">アップグレード</p> 
                </div>
                <div class="bg-black rounded-3xl p-2 mx-5">  
                    <p class="text-white font-bold text-sm">risako</p>
                </div>
            </div>
            <!-- playlist -->
            <div> 
                <h1 class="text-4xl text-white font-bold">こんばんは</h1>
                <div class="flex flex-wrap">
                    <div v-for="playlist in topPlaylist" :key="playlist.title" class="p-3 w-1/3"> 
                        <div class="bg-purple-800 rounded-xl flex">  
                            <img src="../assets/spotify/your-top-songs-2018_DEFAULT-ja.jpg" width="100" class="rounded-xl justify-start"> 
                            <div class="flex justify-center items-center">
                                <p class="ml-4 justify-around text-white font-bold">{{playlist.title}}</p>
                            </div>
                        </div>
                    </div>
                </div>
                <h2 class="text-2xl text-white font-bold">最近再生したコンテンツ</h2> 
                <div> 
                    <div class="flex flex-wrap">  
                        <div v-for="playlist in rescentPlaylist" :key="playlist.title" class="p-3 w-1/4">
                            <div class="bg-black-800 rounded-sm">  
                                <img src="../assets/spotify/region_global_default.jpg" width="300" class="rounded-xl justify-start"> 
                                <div class="">
                                    <p class="ml-4 justify-around text-white font-bold">{{playlist.title}}</p>
                                    <p class="ml-4 justify-around text-white text-xs text-gray-500">{{playlist.description}}</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data: function () {
        return {
            topPlaylist: [
                {
                    image: 'your-top-songs-2018_DEFAULT-ja.jpg',
                    title: "あなたのトップソング 2018"
                },
                {
                    image: 'your-top-songs-2018_DEFAULT-ja.jpg',
                    title: "あなたのトップソング 2018"
                },
                {
                    image: 'your-top-songs-2018_DEFAULT-ja.jpg',
                    title: "あなたのトップソング 2018"
                },
                {
                    image: 'your-top-songs-2018_DEFAULT-ja.jpg',
                    title: "あなたのトップソング 2018"
                },
                {
                    image: 'your-top-songs-2018_DEFAULT-ja.jpg',
                    title: "あなたのトップソング 2018"
                },
                {
                    image: 'your-top-songs-2018_DEFAULT-ja.jpg',
                    title: "あなたのトップソング 2018"
                }
            ],
            rescentPlaylist: [
                {
                    title: "Top K-pop artist of 2019",
                    description: "Top of the top hits this year! Cover:TWICE"
                },
                {
                    title: "EXO Radio",
                    description: "作成者: Spotify"
                }, 
                {
                    title: "SMTOWN Select",
                    description: "作成者: Spotify"
                },
                {
                    title: "あなたのトップソング 2018",
                    description: "作成者: Spotify"
                }
            ]
        }
    },
}
</script>