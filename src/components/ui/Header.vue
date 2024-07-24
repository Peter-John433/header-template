<template>
    <div 
        class="
        bg-black
        text-white
        hidden lg:block
     "
    >
        <div 
            class="
                flex justify-between flex-row items-center
                container
            "
            
        >
            <!-- logo -->
            <div>
                <a 
                    href="#"
                    class="
                        bg-blue-500
                        rounded-full p-2
                        font-bold text-white tracking-[0.5px]
                    "
                >
                    geegip-fx
                </a>
            </div>
            <!-- closed -->
            <nav>
                <ul class=
                    "
                    flex flex-col lg:flex-row
                    justify-between items-center
                    "
                >
                  
                    <a 
                        :href="item.name"
                        v-for="item in navItems"
                        :key="item.id"
                        class="
                            list-none
                            gap-x-4
                            p-4 hover:bg-blue-500
                            capitalize text-[14px]
                        "
                    >
                        {{ item.name }}
                    </a>
                </ul>
            </nav>
        </div>
    </div>
    <!-- mobile-view -->
    <div 
        class="
        text-white
        relative
        p-3
        lg:hidden
        bg-[#0d0d0d]
     "
    >
        <div 
            class="
                flex justify-between items-center
            "
        >
            <!-- logo -->
                <div>
                    <a 
                        href="#"
                        class="
                            bg-blue-500
                            rounded-full p-2
                            font-bold text-white tracking-[0.5px]
                        "
                    >
                        geegip-fx
                    </a>
                </div>
            <!-- closed -->
            <nav>
               
                <ul 
                    v-show="showMenu"
                    class=
                        "
                        flex flex-col
                        justify-between items-center
                        absolute w-full left-0 top-[100%]
                        bg-black pb-20
                        "
                >
                  
                    <a 
                        :href="item.name"
                        v-for="item in navItems"
                        :key="item.id"
                        class="
                            list-none
                            gap-x-4
                            p-4 hover:bg-blue-500
                            capitalize text-[14px]
                            w-full
                        "
                    >
                        {{ item.name }}
                    </a>
                </ul>
            </nav>
            <!-- menu -->
            <div
                @click="toggleMenu"
                class="
                    bg-blue-500
                    rounded-full
                    font-bold text-white tracking-[0.5px]
                    p-1 flex justify-center items-center
                "
            >
                <span v-if="showMenu" class="px-1.5">
                    x
                </span>
                <span v-else>
                    go
                </span>
            </div>
            <!-- closed -->
        </div>
    </div>
    <!-- closed -->
</template>

<script setup>
    import { ref } from 'vue';

    const navItems = ref([
        {
            name: 'home',
            url: '#',
            id: 1
        },
        {
            name: 'about',
            url: '#',
            id: 2
        },
        {
            name: 'profile',
            url: '#',
            id: 3
        },
        {
            name: 'contact',
            url: '#',
            id: 4
        },
        {
            name: 'service',
            url: '#',
            id: 5
        },
    ])

    const showMenu = ref(false);

    const toggleMenu = () =>{
        showMenu.value = !showMenu.value
    }
</script>