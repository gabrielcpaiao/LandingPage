<template>
    <div class="navbar bg-gray-950 shadow-sm">
        <div class="navbar-start">
            <div class="dropdown">
                <div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
                    <img class="mx-auto block h-24 rounded-full sm:mx-0 sm:shrink-0" :src="myPhoto"
                        alt="Profile picture" />
                    <div class="space-y-2 text-center sm:text-left">
                        <div class="space-y-0.5">
                            <p class="text-lg font-semibold text-black">Erin Lindford</p>
                            <p class="font-medium text-gray-500">Product Engineer</p>
                        </div>
                        <button
                            class="border-purple-200 text-purple-600 hover:border-transparent hover:bg-purple-600 hover:text-white active:bg-purple-700 ...">
                            Message
                        </button>
                    </div>
                </div>
                <ul tabindex="0" class="menu menu-sm dropdown-content bg-base-100 rounded-box z-1 mt-3 w-52 p-2 shadow">
                    <li><a>Item 1</a></li>
                    <li>
                        <a>Parent</a>
                        <ul class="p-2">
                            <li><a>Submenu 1</a></li>
                            <li><a>Submenu 2</a></li>
                        </ul>
                    </li>
                    <li><a>Item 3</a></li>
                </ul>
            </div>
            <a class="btn btn-ghost text-xl">daisyUI</a>
        </div>
        <div class="navbar-center hidden lg:flex">
            <ul class="menu menu-horizontal px-1">
                <li><a>Item 1</a></li>
                <li>
                    <details>
                        <summary>Parent</summary>
                        <ul class="p-2">
                            <li><a>Submenu 1</a></li>
                            <li><a>Submenu 2</a></li>
                        </ul>
                    </details>
                </li>
                <li><a>Item 3</a></li>
            </ul>
        </div>
        <div class="flex flex-col gap-2 p-8 sm:flex-row sm:items-center sm:gap-6 sm:py-4 ...">
            <img class="mx-auto block h-24 rounded-full sm:mx-0 sm:shrink-0" :src="myPhoto" alt="Profile picture" />
            <div class="space-y-2 text-center sm:text-left">
                <div class="space-y-0.5">
                    <p class="text-lg font-semibold text-black">Erin Lindford</p>
                    <p class="font-medium text-gray-500">Product Engineer</p>
                </div>
                <button
                    class="border-purple-200 text-purple-600 hover:border-transparent hover:bg-purple-600 hover:text-white active:bg-purple-700 ...">
                    Message
                </button>
            </div>
        </div>
    </div>

</template>


<script setup>
import myPhoto from '../assets/desenho.jpg';
</script>