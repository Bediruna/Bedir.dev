<script>
    import { onMount } from "svelte";
    import LinkedInIcon from "./icons/LinkedInIcon.svelte";
    import GitHubIcon from "./icons/GitHubIcon.svelte";
    import SunIcon from "./icons/SunIcon.svelte";
    import MoonIcon from "./icons/MoonIcon.svelte";

    let theme;

    onMount(() => {
        const savedTheme = localStorage.getItem("theme");
        const prefersDark = window.matchMedia(
            "(prefers-color-scheme: dark)",
        ).matches;
        theme = savedTheme || (prefersDark ? "dark" : "light");
        document.documentElement.setAttribute("data-bs-theme", theme);
    });

    function toggleTheme() {
        theme = theme === "light" ? "dark" : "light";
        document.documentElement.setAttribute("data-bs-theme", theme);
        localStorage.setItem("theme", theme);
    }
</script>

<nav class="navbar navbar-expand-lg">
    <div class="container-fluid">
        <!-- Left nav items -->
        <ul class="navbar-nav me-auto mb-2 mb-lg-0 gap-3">
            <li class="nav-item">
                <a class="nav-link" href="/">BEDIR</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="/work">WORK</a>
            </li>
        </ul>

        <!-- Right nav items -->
        <ul class="navbar-nav ms-auto mb-2 mb-lg-0 gap-3">
            <li class="nav-item">
                <a
                    class="nav-link"
                    href="https://www.linkedin.com/in/BedirAygun"
                    target="_blank"
                    rel="noopener noreferrer"
                    aria-label="LinkedIn profile"
                >
                    <LinkedInIcon />
                </a>
            </li>
            <li class="nav-item">
                <a
                    class="nav-link"
                    href="https://github.com/BedrYusf"
                    target="_blank"
                    rel="noopener noreferrer"
                    aria-label="GitHub profile"
                >
                    <GitHubIcon />
                </a>
            </li>
            <li class="nav-item d-flex">
                <button
                    id="theme-toggle-btn"
                    on:click={toggleTheme}
                    aria-label={theme === "light"
                        ? "Switch to dark mode"
                        : "Switch to light mode"}
                >
                    {#if theme === "light"}
                        <MoonIcon />
                    {:else}
                        <SunIcon />
                    {/if}
                </button>
            </li>
        </ul>
    </div>
</nav>

<style>
    .nav-link {
        font-size: 1.3rem;
        color: var(--text-color) !important;
        display: inline-flex;
        align-items: center;
        justify-content: center;
    }

    #theme-toggle-btn {
        background: none;
        border: none;
        cursor: pointer;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        padding: 0;
        color: var(--icon-color);
        vertical-align: middle;
    }
</style>
