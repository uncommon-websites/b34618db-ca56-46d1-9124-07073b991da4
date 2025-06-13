<script lang="ts">
	// Types
	import type { Snippet } from "svelte";
	import type { ButtonRootProps } from "bits-ui";
	import { Button } from "bits-ui";

	type Variant = "primary" | "secondary" | "ghost";
	type Size = "sm" | "md" | "lg";

	type Props = ButtonRootProps & {
		variant?: Variant;
		size?: Size;
		children: Snippet;
		iconOnly?: boolean;
		hideLabel?: boolean;
		rounded?: boolean;
		prefix?: Snippet;
		suffix?: Snippet;
	};

	// Props
	const {
		variant = "primary",
		size = "md",
		children,
		class: classes = "",
		prefix: Prefix,
		suffix: Suffix,
		iconOnly = false,
		hideLabel = false,
		...rest
	}: Props = $props();

	// Styles - Use design system classes
	const variants: Record<Variant, string> = {
		primary: "",
		secondary: "",
		ghost: ""
	};

	const sizes: Record<Size, string> = $derived({
		sm: iconOnly ? "aspect-square" : "",
		md: iconOnly ? "aspect-square" : "",
		lg: iconOnly ? "aspect-square" : ""
	});

	const baseStyles = iconOnly ? "aspect-square" : "";
</script>

<Button.Root
	{...rest}
	class={[
		baseStyles,
		variants[variant],
		sizes[size],
		classes
	]}
	data-button-root
	data-variant={variant}
	data-size={size}
>
	{#if Prefix}
		<Prefix />
	{/if}
	<span class:sr-only={hideLabel || iconOnly}>
		{@render children?.()}
	</span>
	{#if Suffix}
		<Suffix />
	{/if}
</Button.Root>
