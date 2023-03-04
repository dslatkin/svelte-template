<script lang="ts">
    import Code from '$lib/Code.svelte';

    const source = `
        <script lang="ts">
            let test: 'a' | 'b' | () => boolean = undefined
            console.log(test)
        ${'</' + 'script>'}
        
        <h1>Test</h1>

        <ul>
            <li>Item 1</li>
            <li>Item 2</li>
            <li>Item 3</li>
        </ul>

        <style>
            body {
                background: lightblue;
            }
        </style>
    `;
</script>

<h1>Welcome to your library project</h1>
<p>
    Create your package using @sveltejs/package and preview/showcase your work
    with SvelteKit
</p>
<p>
    Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
</p>
<Code language="svelte" {source} />
