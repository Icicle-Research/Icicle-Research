
<script>
    let links = [
        { name: 'Home', url: '/' },
        { name: 'About', url: '/about' },
        { name: 'Contact', url: '/contact' },
    ];
</script>

<nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-6 sm:px-6 lg:px-8">
        <div class="grid grid-cols-3 h-16 items-center">
            <!-- Logo -->
            <div class="col-span-1">
                <span class="text-white font-semibold text-lg">Logo</span>
            </div>

            <!-- Navigation Links -->
            <div class="col-span-2 hidden md:block">
                <div class="flex justify-end items-baseline">
                    {#each links as link}
                        <a href={link.url} class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">{link.name}</a>
                    {/each}
                </div>
            </div>
        </div>
    </div>
</nav>

