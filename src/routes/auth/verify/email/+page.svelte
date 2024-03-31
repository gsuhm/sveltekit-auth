<script lang="ts">
	import { APP_NAME } from '$lib/config/constants';
	export let data;

	$: userEmail = data?.user?.email || '';
</script>

<section class="container grid items-center gap-6">
	<div class="flex max-w-[980px] flex-col items-start gap-2">
		<h1 class="text-3xl font-extrabold leading-tight tracking-tighter md:text-4xl">
			Confirm Your Email Address
		</h1>
		<p class="max-w-[700px] text-lg text-muted-foreground">
			Please check your email account for a message to confirm your email address for {APP_NAME}. If
			you did not receive the email,
			{#if userEmail}
				<a href="/auth/verify/resend-email-{encodeURIComponent(userEmail)}" class="underline"
					>click here</a
				> to resend it.
			{:else}
				<span>Please provide a valid email.</span>
			{/if}
		</p>
	</div>
</section>
