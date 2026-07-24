<script>
    import { onMount } from "svelte";
    import LinkedInIcon from "./icons/LinkedInIcon.svelte";
    import GitHubIcon from "./icons/GitHubIcon.svelte";
    import SunIcon from "./icons/SunIcon.svelte";
    import MoonIcon from "./icons/MoonIcon.svelte";
    import { calUrl } from "$lib/ContactData.js";

    let theme;

    onMount(() => {
        theme = localStorage.getItem("theme") || "light";
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
        <ul class="navbar-nav ms-auto mb-2 mb-lg-0 gap-3 align-items-center">
            <li class="nav-item">
                <a
                    class="btn-book-nav"
                    href={calUrl}
                    target="_blank"
                    rel="noopener noreferrer"
                >
                    Book a call
                </a>
            </li>
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

    .btn-book-nav {
        display: inline-block;
        padding: 0.35rem 0.85rem;
        font-size: 1rem;
        font-weight: 600;
        text-decoration: none;
        color: var(--background-color);
        background-color: var(--text-color);
        border: 2px solid var(--text-color);
        white-space: nowrap;
    }

    .btn-book-nav:hover {
        opacity: 0.85;
        color: var(--background-color);
    }
</style>
