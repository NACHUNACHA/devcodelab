<script>
    import ai from '$lib/assets/ai.png';
    import codelabs from '$lib/assets/codelabs.png';
</script>

<div class="bg-black h-screen bg-[url('/bg.png')] bg-cover bg-center bg-no-repeat flex justify-center items-center">

    <div class="w-[700px] p-8 text-white flex flex-col items-center justify-center gap-8 rounded-[9px] border-[1px] border-[#1B1B1B] bg-black/80 backdrop-blur-sm">
        <div class="flex flex-col items-center ">
            <p class="text-lg font-semibold">ยินดีต้อนรับ</p>
            <img src={codelabs} alt="CodeLabs Logo" class="w-96"/>
        </div>

        <form class="flex flex-col items-center gap-4 px-20 w-full">
            <div class="w-full flex flex-col gap-1">
                <label for="email" class="text-lg">อีเมล</label>
                <input type="text" id="email" name="email" class="rounded-[5px] p-2 bg-[#090909] text-white w-full" placeholder="กรอกอีเมล"/>
            </div>

            <div class="w-full flex flex-col gap-1">
                <label for="password" class="text-lg">รหัสผ่าน</label>
                <input type="password" id="password" name="password" class="rounded-[5px] p-2 bg-[#090909] text-white" placeholder="กรุณากรอกรหัสผ่าน"/>
            </div>

            <button class="cursor-pointer justify-end">ลืมรหัสผ่าน</button>

            <button type="submit" class="cursor-pointer mt-6 bg-gradient-to-r from-[#5602FE] via-[#34B1FE] to-[#7632FF] text-white font-bold py-2 px-4 rounded-[5px] w-full">
                เข้าสู่ระบบ
            </button>

        </form>
        
        <p class="text-[#696969]">โดยการเข้าสู่ระบบ ถือว่าคุณยอมรับ <span class="text-white">เงื่อนไขการใช้งาน</span> และ <span class="text-white">นโยบายความเป็นส่วนตัว</span></p>
    </div>

</div>