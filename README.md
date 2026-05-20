Name: Xuanye Wang

1. Where would you fit your automated tests in your Recipe project development pipeline? Select one of the following and explain why.

Within a GitHub Action that runs whenever code is pushed. Running tests automatically on every push catches bugs before they get merged into the main branch and ensures every team member's code is verified in a consistent environment. Relying on developers to remember to run tests locally is error-prone, and waiting until all development is done means bugs accumulate and become much harder to debug.

2. Would you use an end-to-end test to check if a function is returning the correct output?

No. E2E tests are meant to simulate full user workflows through the UI, which is slow and too much for verifying a single function's output. A unit test is enough for that, as it isolates the functions and runs in milliseconds.

3. What is the difference between Lighthouse Navigation mode and Snapshot mode?

Navigation mode analyzes a page right after it loads, giving an overall performance score for the initial page load, but it can't measure user interactions or DOM changes after load. Snapshot mode analyzes the page in its current state at the moment you run it. It's best for finding accessibility issues but can't measure JS performance or content changes over time.

4. Three things we could do to improve the CSE 110 shop based on Lighthouse results:

- Although FCP (0.2s) and LCP (0.5s) are great, the page takes 7 seconds for content to be visually populated. Lazy-loading product images below the fold and prefetching the JSON product data would let visible content paint faster.
- The cart count `<span id="cart-count">` has no aria-label, so screen readers can't announce cart updates clearly. Image `alt` text also currently just reuses the raw product title, more descriptive alt text would help SEO and screen reader users.
- Lighthouse flagged `assets/styles/main.css` as a render-blocking request, meaning the browser pauses parsing to fetch and apply it before showing content. Inlining critical CSS in the `<head>` or adding `media`/`onload` attributes to defer non-critical styles would move it out of the critical path and improve LCP.


