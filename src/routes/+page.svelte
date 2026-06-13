<script lang="ts">
	import { config, appTitle } from '$lib/config';

	interface Props {
		data: { user: App.Locals['user'] };
	}
	let { data }: Props = $props();
</script>

<svelte:head>
	<title>{appTitle()}</title>
</svelte:head>

{#if data.user}
	<div class="text-center py-12">
		<p class="text-rok-muted">Chào <span class="text-rok-accent font-semibold">{data.user.username}</span></p>
		<a href="/dashboard" class="btn-primary mt-4 inline-block">Vào Dashboard</a>
	</div>
{:else}
	<div class="flex flex-col items-center justify-center min-h-[70vh] text-center px-4">
		<div class="text-6xl mb-6">⚔️</div>
		<h1 class="text-3xl font-bold text-rok-accent mb-2">{config.kingdomName}</h1>
		<p class="text-rok-muted mb-1">{config.subtitle}</p>
		<p class="text-rok-dim text-sm mb-8">Quản lý tài khoản & đánh giá đóng góp</p>
		<a href="/login" class="btn-primary text-base px-8 py-3">Đăng nhập</a>
	</div>
{/if}
