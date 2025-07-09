<script>
    import ai from '$lib/assets/ai.png';
    import codelabs from '$lib/assets/codelabs.png';
    import { Application } from '@splinetool/runtime';
    import { onMount } from 'svelte';

    let canvas;

    function resizeCanvas() {
        if (canvas) {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight ;
        }
    }

    onMount(() => {
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);

        const app = new Application(canvas);
        app.load("https://prod.spline.design/44RXbIkrQgxHWvur/scene.splinecode");

        return () => {
            window.removeEventListener('resize', resizeCanvas);
        };
    });
</script>

<style>
    .bg-canvas {
        position: fixed;
        inset: 0;
        width: 100vw;
        height: 100vh;
        z-index: 0;
        display: block;
    }
    .content {
        position: relative;
        z-index: 1;
    }
</style>

<canvas bind:this={canvas} class="bg-canvas"></canvas>

<div class="content font-[Kanit] h-screen flex justify-center items-center">
    <div class="w-[700px] p-8 text-white flex flex-col items-center justify-center gap-8 rounded-[9px] border-[1px] border-[#1B1B1B] bg-black/80 backdrop-blur-sm">
        <div class="flex flex-col items-center ">
            <p class="text-xl font-semibold">ยินดีต้อนรับ</p>
            <img src={codelabs} alt="CodeLabs Logo" class="w-96"/>
        </div>

        <form class="flex flex-col items-center gap-6 px-20 w-full">
            <div class="w-full flex flex-col gap-1">
                <label for="email" class="text-lg">อีเมล</label>
                <input type="text" id="email" name="email" class="rounded-[5px] p-2 bg-[#090909] border-[1px] border-[#1B1B1B] text-white w-full" placeholder="กรอกอีเมล"/>
            </div>

            <div class="w-full flex flex-col gap-1">
                <label for="password" class="text-lg">รหัสผ่าน</label>
                <input type="password" id="password" name="password" class="rounded-[5px] p-2 bg-[#090909] border-[1px] border-[#1B1B1B] text-white w-full" placeholder="กรุณากรอกรหัสผ่าน"/>
            </div>

            <div class="w-full flex justify-end">
                <button class="cursor-pointer">ลืมรหัสผ่าน</button>
            </div>

            <button type="submit" class="cursor-pointer bg-gradient-to-r from-[#5602FE] via-[#34B1FE] to-[#7632FF] text-[#CFCFCF] font-bold py-2 px-4 rounded-[5px] w-full">
                เข้าสู่ระบบ
            </button>
        </form>
        
        <p class="text-[#696969]">โดยการเข้าสู่ระบบ ถือว่าคุณยอมรับ <span class="text-white">เงื่อนไขการใช้งาน</span> และ <span class="text-white">นโยบายความเป็นส่วนตัว</span></p>
    </div>
</div>
