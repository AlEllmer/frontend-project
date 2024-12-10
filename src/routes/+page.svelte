<script>
	let testimonials = [
		{
			text: "I've been interested in coding for a while but never taken the jump, until now. I couldn’t recommend this course enough. I’m now in the job of my dreams and so excited about the future.",
			name: 'Tanya Sinclair',
			role: 'UX Engineer',
			image: '/images/image-tanya.jpg'
		},
		{
			text: 'If you want to lay the best foundation possible, I’d recommend this course. The depth the instructors go into is incredible. I now feel so confident about starting up as a professional developer.',
			name: 'John Tarkpor',
			role: 'Junior Frontend Developer',
			image: '/images/image-john.jpg'
		}
	];

	let currentIndex = 0;

	function next() {
		currentIndex = (currentIndex + 1) % testimonials.length;
	}

	function previous() {
		currentIndex = (currentIndex - 1 + testimonials.length) % testimonials.length;
	}
</script>

<div class="min-h-screen flex flex-col items-center justify-center relative bg-white">
	<div
		class="relative max-w-sm w-full p-6 bg-white rounded-2xl shadow-lg flex flex-col items-center"
	>
		<div class="flex flex-col items-center mb-4 h-10">
			<img
				src="/images/pattern-bg.svg"
				alt="Background Pattern"
				class="absolute top-0 z-0 h-[19.5rem]"
			/>
		</div>
		<div>
			<img
				src="/images/pattern-curve.svg"
				alt="Curve Pattern"
				class="absolute bottom-0 left-0 z-0 h-14"
			/>
		</div>

		<div class="z-10 shadow-2xl rounded-lg">
			<img
				class="w-64 h-64 shadow-md rounded-lg mt-[-3rem]"
				src={testimonials[currentIndex].image}
				alt={testimonials[currentIndex].name}
			/>
		</div>

		<div
			class="relative flex justify-center z-20 border-white bottom-6 p-4 w-20 h-10 shadow-lg rounded-full bg-white"
		>
			<button class="absolute left-3 top-3" onclick={previous}>
				<img src="/images/icon-prev.svg" alt="Previous" />
			</button>
			<button class="absolute right-3 top-3" onclick={next}>
				<img src="/images/icon-next.svg" alt="Next" />
			</button>
		</div>
		<img
			src="/images/pattern-quotes.svg"
			alt="Quotes Pattern"
			class="relative left-0 w-16 h-12 mt-4 top-[-1rem]"
		/>
		<div class="mb-4">
			<blockquote class="text-md text-gray-700 mb-2 font-serif text-center mt-[-2.5rem;] z-10">
				"{testimonials[currentIndex].text}"
			</blockquote>
			<div class="flex flex-col items-center text-center z-10">
				<p class="text-sm font-bold text-gray-800">{testimonials[currentIndex].name}</p>
				<span class="text-xs text-gray-400">{testimonials[currentIndex].role}</span>
			</div>
		</div>
	</div>
</div>

<style>
	.min-h-screen {
		position: relative;
	}

	.font-serif {
		font-family: 'Inter' sans-serif;
	}

	@media (max-width: 640px) {
		.text-md {
			font-size: 1rem;
		}
		.text-sm {
			font-size: 0.875rem;
		}
		.text-xs {
			font-size: 0.75rem;
		}
	}
</style>
