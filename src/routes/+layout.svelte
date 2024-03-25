<nav>
    <div class="nav-container">
        <a href="/" class="nav-logo" title="Back to Homepages">Империя Грёз</a>
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
            title: "О кинотеатре",
            href: "/about",
            isShow: true,
        },
        {
            title: "Каталог фильмов",
            href: "/blog",
            isShow: true,
        },
        {
            title: "Описание фильмов",
            href: "/opis",
            isShow: true,
        },
        {
            title: "О нас",
            href: "/contact",
            isShow: true,
        },
    ];
</script>

<style>

        nav {
            background-color: transparent;
            color: #fff;
            padding: 10px 0;
        }
        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
            
        }
        .nav-logo {
            text-decoration: none;
            font-size: 24px;
            font-weight: bold;
            color: #ff0000;
        }
        .nav-links {
            display: flex;
        }
        .nav-links .link {
            text-decoration: none;
            color: #ff0000;
            margin-left: 20px;
        }
        .container {
            max-width: 1400px;
            margin: 50px auto;
            padding: 0 20px;
        }
</style>

