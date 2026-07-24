<script>
    import { onMount } from "svelte";
    import { email, phone, calUrl } from "$lib/ContactData.js";

    const telHref = phone ? `tel:+1${phone.replace(/\D/g, "")}` : "";

    let demoVideo;

    onMount(() => {
        // Svelte's hydration can drop the muted flag, which makes the
        // browser block autoplay; re-assert it and start playback manually.
        if (demoVideo) {
            demoVideo.muted = true;
            demoVideo.play().catch(() => {});
        }
    });
</script>

<div class="page">
    <section class="hero">
        <img
            class="avatar avatar-light"
            src="/avatar-light.jpg"
            alt="Bedir Aygun"
            width="112"
            height="112"
        />
        <img
            class="avatar avatar-dark"
            src="/avatar-dark.jpg"
            alt="Bedir Aygun"
            width="112"
            height="112"
        />
        <p class="status">
            <span class="status-dot"></span>
            Available for new projects
        </p>
        <h1>Bedir Aygun</h1>
        <p class="tagline">Custom Software &amp; AI Automation</p>
        <p class="lead">
            I build software for businesses. Scheduling, invoicing, dispatch,
            automations. Off spreadsheets, off paper.
        </p>
        <div class="hero-actions">
            <a
                class="btn-primary"
                href={calUrl}
                target="_blank"
                rel="noopener noreferrer"
            >
                Book a call
                <svg
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    aria-hidden="true"
                >
                    <path d="M5 12h14" />
                    <path d="m12 5 7 7-7 7" />
                </svg>
            </a>
            <a class="btn-ghost" href="mailto:{email}">
                <svg
                    width="16"
                    height="16"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="1.8"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    aria-hidden="true"
                >
                    <rect x="2" y="4" width="20" height="16" rx="2" />
                    <path d="m22 7-10 6L2 7" />
                </svg>
                {email}
            </a>
        </div>
    </section>

    <section class="section">
        <p class="kicker">What I do</p>
        <div class="cards">
            <article class="card-item">
                <div class="card-icon" aria-hidden="true">
                    <svg
                        width="20"
                        height="20"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="1.8"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                    >
                        <polyline points="16 18 22 12 16 6" />
                        <polyline points="8 6 2 12 8 18" />
                    </svg>
                </div>
                <h3>Custom software</h3>
                <p>
                    I build the tools your business actually needs: scheduling,
                    invoicing, dispatch, and the day-to-day workflows that still
                    live in spreadsheets.
                </p>
            </article>
            <article class="card-item">
                <div class="card-icon" aria-hidden="true">
                    <svg
                        width="20"
                        height="20"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="1.8"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                    >
                        <path
                            d="M12 3v2M12 19v2M5.6 5.6l1.4 1.4M17 17l1.4 1.4M3 12h2M19 12h2M5.6 18.4 7 17M17 7l1.4-1.4"
                        />
                        <circle cx="12" cy="12" r="4" />
                    </svg>
                </div>
                <h3>AI automation</h3>
                <p>
                    I set up automations that take busywork off your plate: data
                    entry, follow-ups, document handling. So people can focus on
                    the work that matters.
                </p>
            </article>
            <article class="card-item">
                <div class="card-icon" aria-hidden="true">
                    <svg
                        width="20"
                        height="20"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="1.8"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                    >
                        <path
                            d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"
                        />
                        <path
                            d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"
                        />
                    </svg>
                </div>
                <h3>Integrations</h3>
                <p>
                    I connect the systems you already use so information moves
                    between them without copy-paste and double entry.
                </p>
            </article>
        </div>
    </section>

    <section class="section">
        <p class="kicker">Featured project</p>
        <a
            class="project-card"
            href="https://territoryscan.com"
            target="_blank"
            rel="noopener noreferrer"
        >
            <div class="project-media">
                <video bind:this={demoVideo} autoplay muted loop playsinline>
                    <track kind="captions" />
                    <source src="/demo.mp4" type="video/mp4" />
                </video>
            </div>
            <div class="project-body">
                <h3>TerritoryScan</h3>
                <p>
                    Lead generation and tech sourcing for HVAC companies, built
                    on public permit and license records.
                </p>
                <span class="project-link">
                    territoryscan.com
                    <svg
                        width="16"
                        height="16"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        aria-hidden="true"
                    >
                        <path d="M5 12h14" />
                        <path d="m12 5 7 7-7 7" />
                    </svg>
                </span>
            </div>
        </a>
    </section>

    <section class="section">
        <p class="kicker">About</p>
        <p class="about-text">
            I've spent <strong>10 years</strong> as a software engineer. I built
            systems for a national auto-services company and for logistics. Now
            I help businesses replace paper and spreadsheets with software that
            fits how they already work.
        </p>
    </section>

    <section class="section">
        <div class="contact-panel">
            <p class="kicker kicker-center">Contact</p>
            <h2>Want to talk about a project?</h2>
            <p class="contact-lead">Book a time that works for you.</p>
            <a
                class="btn-primary btn-large"
                href={calUrl}
                target="_blank"
                rel="noopener noreferrer"
            >
                Book a call
            </a>
            <div class="contact-details">
                {#if phone}
                    <a class="contact-chip" href={telHref}>
                        <span class="chip-icon" aria-hidden="true">
                            <svg
                                width="20"
                                height="20"
                                viewBox="0 0 24 24"
                                fill="none"
                                stroke="currentColor"
                                stroke-width="1.8"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                            >
                                <path
                                    d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
                                />
                            </svg>
                        </span>
                        {phone}
                    </a>
                {/if}
                <a class="contact-chip" href="mailto:{email}">
                    <span class="chip-icon" aria-hidden="true">
                        <svg
                            width="20"
                            height="20"
                            viewBox="0 0 24 24"
                            fill="none"
                            stroke="currentColor"
                            stroke-width="1.8"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                        >
                            <rect x="2" y="4" width="20" height="16" rx="2" />
                            <path d="m22 7-10 6L2 7" />
                        </svg>
                    </span>
                    {email}
                </a>
            </div>
        </div>
    </section>
</div>

<style>
    .page {
        padding-bottom: 5rem;
    }

    /* ---------- Hero ---------- */

    .hero {
        position: relative;
        padding: clamp(3rem, 8vw, 5.5rem) 0 clamp(2.5rem, 6vw, 4rem);
    }

    .hero::before {
        content: "";
        position: absolute;
        inset: -12rem -1rem 0;
        background: radial-gradient(
            42rem 26rem at 18% 0%,
            var(--accent-soft),
            transparent 65%
        );
        pointer-events: none;
    }

    .hero > * {
        position: relative;
    }

    .avatar {
        display: block;
        width: 7rem;
        height: 7rem;
        border-radius: 50%;
        object-fit: cover;
        border: 3px solid var(--background-color);
        box-shadow:
            0 0 0 2px var(--accent-color),
            0 10px 30px -12px rgba(0, 0, 0, 0.4);
        margin-bottom: 1.5rem;
    }

    @media (max-width: 480px) {
        .avatar {
            width: 6rem;
            height: 6rem;
        }
    }

    .avatar-dark {
        display: none;
    }

    :global([data-bs-theme="dark"]) .avatar-light {
        display: none;
    }

    :global([data-bs-theme="dark"]) .avatar-dark {
        display: block;
    }

    .status {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        border: 1px solid var(--border-color);
        border-radius: 999px;
        padding: 0.3rem 0.85rem;
        font-size: 0.82rem;
        font-weight: 500;
        color: var(--muted-color);
        background-color: var(--surface-color);
        margin-bottom: 1.5rem;
    }

    .status-dot {
        width: 0.5rem;
        height: 0.5rem;
        border-radius: 50%;
        background-color: #22c55e;
        box-shadow: 0 0 0 0 rgba(34, 197, 94, 0.5);
        animation: pulse 2.4s ease-out infinite;
    }

    @keyframes pulse {
        0% {
            box-shadow: 0 0 0 0 rgba(34, 197, 94, 0.45);
        }
        70% {
            box-shadow: 0 0 0 0.45rem rgba(34, 197, 94, 0);
        }
        100% {
            box-shadow: 0 0 0 0 rgba(34, 197, 94, 0);
        }
    }

    @media (prefers-reduced-motion: reduce) {
        .status-dot {
            animation: none;
        }
    }

    .hero h1 {
        font-size: clamp(2.6rem, 7vw, 4rem);
        font-weight: 800;
        letter-spacing: -0.03em;
        line-height: 1.05;
        margin-bottom: 0.5rem;
    }

    .tagline {
        font-size: clamp(1.1rem, 2.5vw, 1.35rem);
        font-weight: 600;
        color: var(--accent-color);
        letter-spacing: -0.01em;
        margin-bottom: 1.25rem;
    }

    .lead {
        font-size: 1.15rem;
        line-height: 1.65;
        color: var(--muted-color);
        max-width: 36em;
        margin-bottom: 2rem;
    }

    .hero-actions {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        gap: 0.85rem;
    }

    @media (max-width: 480px) {
        .hero {
            padding-top: 2rem;
        }

        .hero-actions {
            flex-direction: column;
            align-items: stretch;
        }

        .hero-actions .btn-primary,
        .hero-actions .btn-ghost {
            justify-content: center;
        }
    }

    /* ---------- Buttons ---------- */

    .btn-primary {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.75rem 1.5rem;
        font-size: 1rem;
        font-weight: 600;
        text-decoration: none;
        color: var(--background-color);
        background-color: var(--text-color);
        border: 1px solid var(--text-color);
        border-radius: 0.65rem;
        transition:
            transform 0.15s ease,
            box-shadow 0.15s ease,
            opacity 0.15s ease;
    }

    .btn-primary:hover {
        color: var(--background-color);
        transform: translateY(-1px);
        box-shadow: 0 8px 20px -8px rgba(0, 0, 0, 0.4);
        opacity: 0.92;
    }

    .btn-primary svg {
        transition: transform 0.15s ease;
    }

    .btn-primary:hover svg {
        transform: translateX(2px);
    }

    .btn-large {
        padding: 0.9rem 2rem;
        font-size: 1.1rem;
    }

    .btn-ghost {
        display: inline-flex;
        align-items: center;
        gap: 0.5rem;
        padding: 0.75rem 1.5rem;
        font-size: 1rem;
        font-weight: 500;
        text-decoration: none;
        color: var(--text-color);
        border: 1px solid var(--border-color);
        border-radius: 0.65rem;
        transition:
            border-color 0.15s ease,
            background-color 0.15s ease;
    }

    .btn-ghost:hover {
        color: var(--text-color);
        border-color: var(--accent-color);
        background-color: var(--accent-soft);
    }

    :is(.btn-primary, .btn-ghost):focus-visible {
        outline: 2px solid var(--accent-color);
        outline-offset: 2px;
    }

    /* ---------- Sections ---------- */

    .section {
        margin-top: clamp(3.5rem, 8vw, 5.5rem);
    }

    .kicker {
        display: flex;
        align-items: center;
        gap: 0.75rem;
        font-size: 0.8rem;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 0.14em;
        color: var(--muted-color);
        margin-bottom: 1.5rem;
    }

    .kicker::before {
        content: "";
        width: 1.75rem;
        height: 2px;
        background-color: var(--accent-color);
        border-radius: 1px;
    }

    .kicker-center {
        justify-content: center;
        margin-bottom: 1rem;
    }

    /* ---------- Cards ---------- */

    .cards {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(13rem, 1fr));
        gap: 1rem;
    }

    .card-item {
        border: 1px solid var(--border-color);
        border-radius: 1rem;
        background-color: var(--surface-color);
        padding: 1.6rem 1.5rem;
        transition:
            transform 0.18s ease,
            border-color 0.18s ease;
    }

    .card-item:hover {
        transform: translateY(-3px);
        border-color: var(--accent-color);
    }

    .card-icon {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 2.6rem;
        height: 2.6rem;
        border-radius: 0.75rem;
        color: var(--accent-color);
        background-color: var(--accent-soft);
        margin-bottom: 1.1rem;
    }

    .card-item h3 {
        font-size: 1.05rem;
        font-weight: 700;
        letter-spacing: -0.01em;
        margin-bottom: 0.6rem;
    }

    .card-item p {
        font-size: 0.95rem;
        line-height: 1.65;
        color: var(--muted-color);
        margin-bottom: 0;
    }

    /* ---------- Featured project ---------- */

    .project-card {
        display: grid;
        grid-template-columns: 1.25fr 1fr;
        align-items: center;
        overflow: hidden;
        text-decoration: none;
        color: var(--text-color);
        border: 1px solid var(--border-color);
        border-radius: 1rem;
        background-color: var(--surface-color);
        transition:
            transform 0.18s ease,
            border-color 0.18s ease;
    }

    .project-card:hover {
        transform: translateY(-3px);
        border-color: var(--accent-color);
        color: var(--text-color);
    }

    .project-card:focus-visible {
        outline: 2px solid var(--accent-color);
        outline-offset: 2px;
    }

    .project-media {
        align-self: center;
        border-right: 1px solid var(--border-color);
    }

    .project-media video {
        display: block;
        width: 100%;
        height: auto;
    }

    .project-body {
        padding: 1.75rem;
    }

    .project-body h3 {
        font-size: 1.25rem;
        font-weight: 700;
        letter-spacing: -0.01em;
        margin-bottom: 0.6rem;
    }

    .project-body p {
        font-size: 0.95rem;
        line-height: 1.65;
        color: var(--muted-color);
        margin-bottom: 1.1rem;
    }

    .project-link {
        display: inline-flex;
        align-items: center;
        gap: 0.4rem;
        font-size: 0.95rem;
        font-weight: 600;
        color: var(--accent-color);
    }

    .project-link svg {
        transition: transform 0.15s ease;
    }

    .project-card:hover .project-link svg {
        transform: translateX(3px);
    }

    @media (max-width: 767px) {
        .project-card {
            grid-template-columns: 1fr;
        }

        .project-media {
            align-self: start;
            border-right: none;
            border-bottom: 1px solid var(--border-color);
        }
    }

    /* ---------- About ---------- */

    .about-text {
        font-size: 1.2rem;
        line-height: 1.75;
        max-width: 42em;
        margin-bottom: 0;
    }

    .about-text strong {
        font-weight: 700;
    }

    /* ---------- Contact ---------- */

    .contact-panel {
        position: relative;
        overflow: hidden;
        text-align: center;
        border: 1px solid var(--border-color);
        border-radius: 1.25rem;
        background-color: var(--surface-color);
        padding: clamp(2.25rem, 6vw, 3.5rem) 1.5rem;
    }

    .contact-panel::before {
        content: "";
        position: absolute;
        inset: 0;
        background: radial-gradient(
            30rem 14rem at 50% 0%,
            var(--accent-soft),
            transparent 70%
        );
        pointer-events: none;
    }

    .contact-panel > * {
        position: relative;
    }

    .contact-panel h2 {
        font-size: clamp(1.5rem, 4vw, 2rem);
        font-weight: 700;
        letter-spacing: -0.02em;
        margin-bottom: 0.5rem;
    }

    .contact-lead {
        color: var(--muted-color);
        font-size: 1.05rem;
        margin-bottom: 1.75rem;
    }

    .contact-details {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 0.75rem;
        margin-top: 1.75rem;
    }

    .contact-chip {
        display: inline-flex;
        align-items: center;
        gap: 0.65rem;
        min-height: 3rem;
        padding: 0.6rem 1.25rem;
        font-size: 1rem;
        font-weight: 500;
        text-decoration: none;
        color: var(--text-color);
        background-color: var(--background-color);
        border: 1px solid var(--border-color);
        border-radius: 0.75rem;
        transition:
            border-color 0.15s ease,
            background-color 0.15s ease;
    }

    .contact-chip:hover {
        color: var(--text-color);
        border-color: var(--accent-color);
        background-color: var(--accent-soft);
    }

    .contact-chip:focus-visible {
        outline: 2px solid var(--accent-color);
        outline-offset: 2px;
    }

    .chip-icon {
        display: inline-flex;
        color: var(--accent-color);
    }

    @media (max-width: 480px) {
        .contact-details {
            flex-direction: column;
            align-items: stretch;
        }

        .contact-chip {
            justify-content: center;
        }
    }
</style>
