<script lang="ts">
	import type { ComponentType } from "svelte";

	interface Props {
		title?: string;
		description?: string;
		icon?: ComponentType;
		iconClass?: string;
		imageSrc?: string;
		imageAspect?: "16/9" | "9/16";
		class?: string;
	}

	let {
		title = "",
		description = "",
		icon,
		iconClass = "size-5 text-primary",
		imageSrc,
		imageAspect = "16/9",
		class: customClass = ""
	}: Props = $props();
</script>

<article
	class="bg-card hover:bg-card-hover border-border flex flex-col text-pretty transition duration-300 ease-out {customClass}"
	style="border-radius: var(--radius); border: 1px solid var(--color-border); padding: 1rem 1.25rem;"
>
	{#if icon || imageSrc}
		<div class="mb-8">
			{#if icon && imageSrc}
				<div class="relative">
					<img
						src={imageSrc}
						alt={title}
						class="w-full object-cover {imageAspect === '9/16' ? 'aspect-[9/16]' : 'aspect-[16/9]'}"
						style="border-radius: max(2px, calc(var(--radius) - 1rem));"
					/>
					<div
						class="absolute top-3 left-3 p-1.5 backdrop-blur-sm"
						style="border-radius: var(--radius-sm); background-color: var(--color-background);"
					>
						<svelte:component
							this={icon}
							class="size-4 {iconClass.includes('text-')
								? iconClass.split(' ').find((c) => c.startsWith('text-'))
								: 'text-primary'}"
						/>
					</div>
				</div>
			{:else if icon}
				<svelte:component this={icon} class={iconClass} />
			{:else if imageSrc}
				<img
					src={imageSrc}
					alt={title}
					class="w-full object-cover {imageAspect === '9/16' ? 'aspect-[9/16]' : 'aspect-[16/9]'}"
					style="border-radius: max(2px, calc(var(--radius) - 1rem));"
				/>
			{/if}
		</div>
	{/if}

	<div class:mt-auto={icon || imageSrc}>
		<h3 class="text-title3 mb-2">
			{title}
		</h3>
		<p class="text-body max-w-prose text-muted-foreground">{description}</p>
	</div>
</article>
