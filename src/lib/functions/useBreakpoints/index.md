---
section: Browser
---

Reactive viewport breakpoints

## Example

<script>
  import Example from './example.svelte'
</script>

<Example />

## Usages

```svelte
<script>
	import { useBreakpoints, breakpointsTailwind } from 'svegos';

	const breakpoints = useBreakpoints(breakpointsTailwind);

	const smAndLarger = breakpoints.greaterOrEqual('sm'); // sm and larger
	const largerThanSm = breakpoints.greater('sm'); // only larger than sm
	const lgAndSmaller = breakpoints.smallerOrEqual('lg'); // lg and smaller
	const smallerThanLg = breakpoints.smaller('lg'); // only smaller than lg
</script>
```

```svelte
<script>
	import { useBreakpoints } from 'svegos';

	const breakpoints = useBreakpoints({
		mobile: 0, // optional
		tablet: 640,
		laptop: 1024,
		desktop: 1280
	});

	// Can be 'mobile' or 'tablet' or 'laptop' or 'desktop'
	const activeBreakpoint = breakpoints.active();

	// true or false
	const laptop = breakpoints.between('laptop', 'desktop');
</script>

<div class={activeBreakpoint}>...</div>
```
