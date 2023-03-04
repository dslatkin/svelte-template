<script lang="ts">
    import Prism from 'prismjs';
    import 'prismjs/themes/prism.css';
    import 'prismjs/plugins/normalize-whitespace/prism-normalize-whitespace.js';
    import 'prismjs/components/prism-javascript.js';
    import 'prismjs/components/prism-typescript.js';
    import 'prism-svelte';

    export let language: 'js' | 'ts' | 'svelte';
    export let source: string;

    $: formatted = format(source);

    const format = (source: string) => {
        // https://prismjs.com/plugins/normalize-whitespace
        const trimmed = Prism.plugins.NormalizeWhitespace.normalize(source, {
            'remove-trailing': true,
            'remove-indent': true,
            'left-trim': true,
            'right-trim': true,
        });

        return Prism.highlight(trimmed, Prism.languages[language], language);
    };
</script>

<pre><code>{@html formatted}</code></pre>
