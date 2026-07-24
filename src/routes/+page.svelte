<script>
    import { email, phone, calUrl } from "$lib/ContactData.js";
</script>

<div class="container pb-5">
    <section class="hero mb-5">
        <h1>Bedir Aygun</h1>
        <h2>Custom Software &amp; AI Automation</h2>
        <p class="lead">
            I build software for businesses. Scheduling, invoicing, dispatch,
            automations. Off spreadsheets, off paper.
        </p>
    </section>

    <section class="my-5">
        <h2>What I do</h2>
        <div class="row g-4 mt-1">
            <div class="col-md-4">
                <h5>Custom software</h5>
                <p>
                    I build the tools your business actually needs: scheduling,
                    invoicing, dispatch, and the day-to-day workflows that still
                    live in spreadsheets.
                </p>
            </div>
            <div class="col-md-4">
                <h5>AI automation</h5>
                <p>
                    I set up automations that take busywork off your plate:
                    data entry, follow-ups, document handling. So people can
                    focus on the work that matters.
                </p>
            </div>
            <div class="col-md-4">
                <h5>Integrations</h5>
                <p>
                    I connect the systems you already use so information moves
                    between them without copy-paste and double entry.
                </p>
            </div>
        </div>
    </section>

    <section class="my-5">
        <h2>About</h2>
        <p>
            I've spent 10 years as a software engineer. I built systems for a
            national auto-services company and for logistics. Now I help
            businesses replace paper and spreadsheets with software that fits
            how they already work.
        </p>
    </section>

    <section class="my-5">
        <h2>Contact</h2>
        <p class="mb-4">
            Want to talk about a project? Book a time that works for you.
        </p>
        <a
            class="btn btn-book btn-lg mb-4"
            href={calUrl}
            target="_blank"
            rel="noopener noreferrer"
        >
            Book a call
        </a>
        <div class="contact-plain">
            {#if phone}
                <p class="mb-1">{phone}</p>
            {/if}
            <p class="mb-0">
                <a href="mailto:{email}">{email}</a>
            </p>
        </div>
    </section>
</div>

<style>
    .hero h1 {
        margin-bottom: 0.25rem;
    }

    .hero h2 {
        font-weight: 400;
        margin-bottom: 1rem;
    }

    .lead {
        font-size: 1.15rem;
        max-width: 36em;
    }

    .btn-book {
        display: inline-block;
        padding: 0.85rem 1.75rem;
        font-size: 1.25rem;
        font-weight: 600;
        text-decoration: none;
        color: var(--background-color);
        background-color: var(--text-color);
        border: 2px solid var(--text-color);
    }

    .btn-book:hover {
        opacity: 0.85;
        color: var(--background-color);
    }

    .contact-plain a {
        color: var(--text-color);
    }
</style>
