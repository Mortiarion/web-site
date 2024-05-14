<script lang="ts">
	import Logo from '$lib/components/base/Logo.svelte';
	import Button from '$lib/components/base/Button.svelte';
	import Link from '$lib/components/base/Link.svelte';
</script>

<nav class="flex items-center pr-5">
	<Logo />
	<ul class="ml-auto flex gap-5 font-bold text-white">
		<li>
			<Link href="#">Головна</Link>
		</li>
		<li>
			<button class="triangle flex items-center">Лінкбилдінг</button>
		</li>
		<li>
			<button class="triangle flex items-center">Компанія</button>
		</li>
		<li>
			<Link href="#">Новини</Link>
		</li>
		<li>
			<Link href="#">Біржа</Link>
		</li>
	</ul>
	<hr class="mx-5 h-10 min-w-0.5 bg-slate-300" />
	<ul class="flex items-center gap-5">
		<li><button class="triangle flex items-center font-bold text-white">Uk</button></li>
		<li>
			<Link href="#">
				<svg
					width="20"
					height="20"
					viewBox="0 0 20 20"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M1 1H1.26835C1.74213 1 1.97943 1 2.17267 1.08548C2.34304 1.16084 2.48871 1.28218 2.59375 1.43604C2.71269 1.61026 2.75564 1.8429 2.84137 2.30727L5.00004 14L15.4218 14C15.875 14 16.1023 14 16.29 13.9199C16.4559 13.8492 16.5989 13.7346 16.7051 13.5889C16.8252 13.4242 16.8761 13.2037 16.9777 12.7631L16.9785 12.76L18.5477 5.95996L18.5481 5.95854C18.7023 5.29016 18.7796 4.95515 18.6947 4.69238C18.6202 4.46182 18.4635 4.26634 18.2556 4.14192C18.0184 4 17.6758 4 16.9887 4H3.5M16 19C15.4477 19 15 18.5523 15 18C15 17.4477 15.4477 17 16 17C16.5523 17 17 17.4477 17 18C17 18.5523 16.5523 19 16 19ZM6 19C5.44772 19 5 18.5523 5 18C5 17.4477 5.44772 17 6 17C6.55228 17 7 17.4477 7 18C7 18.5523 6.55228 19 6 19Z"
						stroke="white"
						stroke-width="2"
						stroke-linecap="round"
						stroke-linejoin="round"
					/>
				</svg>
			</Link>
		</li>
		<li>
			<button class="btn-sign flex items-center gap-5 rounded-full bg-white pr-5">
				<svg
					width="39"
					height="40"
					viewBox="0 0 39 40"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M19.5 39.0244C30.2696 39.0244 39 30.5069 39 20C39 9.4931 30.2696 0.975586 19.5 0.975586C8.73045 0.975586 0 9.4931 0 20C0 30.5069 8.73045 39.0244 19.5 39.0244ZM16.2987 7.86962C15.9034 7.48394 15.2703 7.49176 14.8846 7.88708C14.4989 8.28239 14.5067 8.91551 14.902 9.30118L25.8684 20L14.902 30.6989C14.5067 31.0846 14.4989 31.7177 14.8846 32.113C15.2703 32.5083 15.9034 32.5161 16.2987 32.1304L27.9987 20.7158C28.1916 20.5276 28.3004 20.2695 28.3004 20C28.3004 19.7305 28.1916 19.4724 27.9987 19.2843L16.2987 7.86962Z"
						fill="url(#paint0_linear_59_47)"
					/>
					<defs>
						<linearGradient
							id="paint0_linear_59_47"
							x1="0"
							y1="20"
							x2="39"
							y2="20"
							gradientUnits="userSpaceOnUse"
						>
							<stop stop-color="#11275F" />
							<stop offset="1" stop-color="#1F5EDB" />
						</linearGradient>
					</defs>
				</svg>

				<span class="pl-8 font-bold">Війти</span>
			</button>
		</li>
	</ul>
</nav>

<style lang="postcss">
	nav {
		background: linear-gradient(90deg, #11275f 0%, #1f5edb 100%);
	}
	.btn-sign {
		border: 1px solid white;
		position: relative;
		padding: 7px 20px;
		overflow: hidden;
	}
	.btn-sign:hover {
	}
	.btn-sign svg {
		position: absolute;
		left: 0;
		background-color: white;
		border-radius: 100%;
		border: 1px solid white;
		transition: transform 1.3s ease;
		z-index: 2;
	}
	.btn-sign:hover svg {
		transform: translateX(81px);
	}
	.btn-sign span {
		z-index: 1;
		transition:
			transform 1.3s ease,
			color 1.3s ease;
	}
	.btn-sign:hover span {
		transform: translateX(-31px);
		color: white;
	}
	.btn-sign::before {
		content: '';
		position: absolute;
		top: 0;
		left: -101%;
		border-radius: 0 20px 20px 0;
		width: 100%;
		height: 100%;
		background: linear-gradient(90deg, #11275f 0%, #1f5edb 100%);
		transform: translateX(0%);
		transition: left 1.3s ease;
	}
	.btn-sign:hover::before {
		left: 0%;
	}
	.triangle:after {
		content: '';
		border-left: 6px solid transparent;
		border-right: 6px solid transparent;
		border-top: 6px solid white;
		margin-left: 10px;
		/* height: 10px; */
		/* display: inline-block; */
	}
</style>
