<script>
	export let title;
	export let img = '';

	$: if (title.includes(' ')) title = title.replaceAll(' ', '%20');

	let url = window.location.href;

	import WhatsApp from './icons/whatsapp.svelte';
	import Facebook from './icons/facebook.svelte';
	import Twitter from './icons/twitter.svelte';
	import LinkedIn from './icons/linkedin.svelte';
	import Reddit from './icons/reddit.svelte';
	import Pinterest from './icons/pinterest.svelte';
</script>

{#if title && url}
	<div id="socialShare" class="mt-4">
		<a
			class="icon whatsapp"
			href={'whatsapp://send?text=' + url}
			data-action="share/whatsapp/share"
			target="_blank"
			rel="noopener"
		>
			<WhatsApp title="Lähetä linkki kaverille" />
		</a>

		<a
			class="icon facebook"
			href={'https://facebook.com/sharer/sharer.php?u=' + url}
			target="_blank"
			rel="noopener"
			aria-label="Share on Facebook"
		>
			<Facebook title="Jaa linkki Facebookissa" />
		</a>

		<a
			class="icon twitter"
			href={'https://twitter.com/intent/tweet/?text=' +
				title +
				'&amp;hashtags=foodis&amp;url=' +
				url}
			target="_blank"
			rel="noopener"
			aria-label="Share on Twitter"
		>
			<Twitter title="Jaa linkki Twitterissä" />
		</a>

		<a
			class="icon linkedin"
			href="https://www.linkedin.com/sharing/share-offsite/?url=http://jsdom.ssr/kana/kalkkunaviillokki"
			target="_blank"
			rel="noopener"
			aria-label="Share on LinkedIn"
		>
			<LinkedIn title="Jaa Linkkarissa" />
		</a>

		<a
			class="icon reddit"
			href="https://reddit.com/submit/?url=http://jsdom.ssr/kana/kalkkunaviillokki&amp;resubmit=true&amp;title=Kalkkunaviillokki"
			target="_blank"
			rel="noopener"
			aria-label="Share on Reddit"
		>
			<Reddit title="Jaa Redditissä" />
		</a>

		{#if img}
			<a
				class="icon pinterest"
				href={'https://pinterest.com/pin/create/button/?url=' +
					url +
					'&amp;media=' +
					img +
					'&amp;description=' +
					title}
				target="_blank"
				rel="noopener"
				aria-label="Share on Pinterest"
			>
				<Pinterest title="Jaa Pinterestissä" />
			</a>
		{/if}
	</div>
{/if}

<style>
	#socialShare .icon {
		width: 38px;
		height: 38px;
		display: inline-block;
		margin-right: 2px;
		border-radius: 4px;
		padding: 5px;
		fill: rgba(255, 255, 255, 0.87);
	}
	.whatsapp {
		background-color: #25d366;
	}
	.whatsapp:hover {
		background-color: #1da851;
	}
	.facebook {
		background-color: #3b5998;
	}
	.facebook:hover {
		background-color: #2d4373;
	}
	.twitter {
		background-color: #55acee;
	}
	.twitter:hover {
		background-color: #2795e9;
	}
	.linkedin {
		background-color: #0077b5;
	}
	.linkedin:hover {
		background-color: #046293;
	}
	.reddit {
		background-color: #5f99cf;
	}
	.reddit:hover {
		background-color: #3a80c1;
	}
	.pinterest {
		background-color: #bd081c;
	}
	.pinterest:hover {
		background-color: #8c0615;
	}
</style>
