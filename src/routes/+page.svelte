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

	const next = () => {
		currentIndex = (currentIndex + 1) % testimonials.length;
	};

	const previous = () => {
		currentIndex = (currentIndex - 1 + testimonials.length) % testimonials.length;
	};
</script>

<div class="min-h-screen flex flex-col items-center justify-center relative bg-white">
	<!-- Background Patterns -->
	<img
		src="/images/pattern-bg.svg"
		alt="Background Pattern"
		class="absolute top-0 left-0 w-full h-full object-cover"
	/>
	<img
		src="/images/pattern-curve.svg"
		alt="Curve Pattern"
		class="absolute bottom-0 left-0 w-full"
	/>

	<div
		class="relative max-w-sm w-full p-6 bg-white rounded-2xl shadow-lg flex flex-col items-center z-10"
	>
		<img
			class="w-56 h-56 rounded-lg shadow-md mb-4"
			src={testimonials[currentIndex].image}
			alt={testimonials[currentIndex].name}
		/>
		<img
			src="/images/pattern-quotes.svg"
			alt="Quotes Pattern"
			class="absolute top-0 left-0 w-20 h-20"
		/>
		<blockquote class="text-md text-gray-700 italic mb-2 font-serif text-center">
			<!-- Made text smaller and centered -->
			"{testimonials[currentIndex].text}"
		</blockquote>
		<div class="flex flex-col items-center text-center">
			<!-- Centered text container -->
			<p class="text-sm font-bold text-gray-800">{testimonials[currentIndex].name}</p>
			<!-- Made text smaller -->
			<span class="text-xs text-gray-500">({testimonials[currentIndex].role})</span>
			<!-- Made text smaller -->
		</div>

		<!-- Buttons positioned directly below the text -->
		<div class="flex justify-center mt-4 z-10">
			<button class="btn-circle" onclick={previous}>
				<img src="/images/icon-prev.svg" alt="Previous" />
			</button>
			<button class="btn-circle" onclick={next}>
				<img src="/images/icon-next.svg" alt="Next" />
			</button>
		</div>
	</div>
</div>

<style>
	.min-h-screen {
		position: relative;
	}

	.btn-circle {
		width: 50px;
		height: 50px;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		border: none;
		background-color: #f7f7f7;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
		transition: background-color 0.3s;
		cursor: pointer;
		margin: 0; /* Remove margin to connect buttons */
	}

	.btn-circle:hover {
		background-color: #e2e2e2;
	}

	.btn-circle img {
		width: 24px;
		height: 24px;
	}

	.font-serif {
		font-family: 'Georgia', serif; /* Example font, change as needed */
	}

	/* Responsive adjustments */
	@media (max-width: 640px) {
		.text-md {
			font-size: 1rem; /* Smaller font size for quote */
		}
		.text-sm {
			font-size: 0.875rem; /* Smaller font size for name */
		}
		.text-xs {
			font-size: 0.75rem; /* Smaller font size for role */
		}
	}
</style>
