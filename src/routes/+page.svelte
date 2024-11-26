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
	<div class="relative max-w-4xl w-full p-12 bg-white rounded-2xl shadow-lg flex items-center z-10">
		<div class="flex-1 text-left pr-8">
			<blockquote class="text-xl text-gray-700 italic mb-6 font-serif">
				"{testimonials[currentIndex].text}"
			</blockquote>
			<div class="flex items-center">
				<p class="text-xl font-bold text-gray-800">{testimonials[currentIndex].name}</p>
				<span class="text-md text-gray-500 ml-4">({testimonials[currentIndex].role})</span>
			</div>
		</div>
		<img
			class="w-64 h-64 rounded-lg border-4 border-gray-300 shadow-md"
			src={testimonials[currentIndex].image}
			alt={testimonials[currentIndex].name}
		/>
	</div>
	<div class="flex justify-center mt-4 z-10">
		<button class="btn-circle" onclick={previous}>
			<img src="/images/icon-prev.svg" alt="Previous" />
		</button>
		<button class="btn-circle" onclick={next}>
			<img src="/images/icon-next.svg" alt="Next" />
		</button>
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
</style>
