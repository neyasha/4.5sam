<nav>
    <div class = "nav-container">
        <a href="/" class ="nav-logo" title="Back to Homepages">Настя Палагина</a>
        <div class="nav-links">
            {#each nav as link}
                {#if link.isShow}
                    <a href={link.href} class="link">{link.title}</a>
                    <span>&nbsp;&nbsp;&nbsp;</span>
                {/if}
            {/each}
        </div>
    </div>
</nav>

<div class="container">
    <slot></slot>
</div>
<script>
    const nav = [
        {
         title: "Виды программистов",
         href: "/about",
         isShow: true,
        },
        {
         title: "Обучение",
         href: "/blog",
         isShow: true,
        },
        {
         title: "Перспективы",
         href: "/project",
         isShow: true,
        },
        {
         title: "Итог",
         href: "/contact",
         isShow: true,
        },
        {
         title: "temp",
         href: "/temp",
         isShow: false,
        },
    ];
</script>
<style>
    .container{
        max-width: 1400px;
        margin: 50 px auto;
    }
</style>