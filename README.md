<!DOCTYPE html>
<html lang="ru">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Магазин - Товар со скидкой</title>
	<style>
		* {
			margin: 0;
			padding: 0;
			box-sizing: border-box;
			font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		}

		body {
			background-color: #f8f9fa;
			color: #333;
			line-height: 1.6;
		}

		.container {
			max-width: 1200px;
			margin: 0 auto;
			padding: 20px;
		}

		header {
			background-color: #fff;
			box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
			padding: 15px 0;
			margin-bottom: 30px;
		}

		.header-content {
			display: flex;
			justify-content: space-between;
			align-items: center;
		}

		.logo {
			font-size: 24px;
			font-weight: bold;
			color: #2c3e50;
		}

		.product-section {
			display: flex;
			flex-wrap: wrap;
			gap: 30px;
			margin-bottom: 40px;
		}

		.product-image {
			flex: 1;
			min-width: 300px;
			background-color: #fff;
			border-radius: 10px;
			padding: 20px;
			box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
			text-align: center;
		}

		.product-image img {
			max-width: 100%;
			height: auto;
			border-radius: 5px;
		}

		.product-details {
			flex: 1;
			min-width: 300px;
			background-color: #fff;
			border-radius: 10px;
			padding: 30px;
			box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
		}

		.product-title {
			font-size: 28px;
			margin-bottom: 15px;
			color: #2c3e50;
		}

		.price-section {
			margin-bottom: 25px;
		}

		.original-price {
			font-size: 18px;
			color: #7f8c8d;
			text-decoration: line-through;
			margin-right: 10px;
		}

		.discount-price {
			font-size: 32px;
			color: #e74c3c;
			font-weight: bold;
		}

		.discount-badge {
			display: inline-block;
			background-color: #e74c3c;
			color: white;
			padding: 5px 10px;
			border-radius: 4px;
			font-size: 14px;
			margin-left: 10px;
			vertical-align: middle;
		}

		.size-section {
			margin-bottom: 25px;
		}

		.size-title {
			font-size: 18px;
			margin-bottom: 10px;
			color: #2c3e50;
		}

		.size-options {
			display: flex;
			gap: 10px;
			flex-wrap: wrap;
		}

		.size-option {
			width: 50px;
			height: 50px;
			border: 2px solid #ddd;
			border-radius: 5px;
			display: flex;
			align-items: center;
			justify-content: center;
			cursor: pointer;
			transition: all 0.3s ease;
		}

		.size-option:hover {
			border-color: #3498db;
		}

		.size-option.selected {
			background-color: #3498db;
			color: white;
			border-color: #3498db;
		}

		.buy-button {
			background-color: #3498db;
			color: white;
			border: none;
			padding: 15px 30px;
			font-size: 18px;
			border-radius: 5px;
			cursor: pointer;
			transition: background-color 0.3s ease;
			width: 100%;
			margin-top: 20px;
		}

		.buy-button:hover {
			background-color: #2980b9;
		}

		.reviews-section {
			background-color: #fff;
			border-radius: 10px;
			padding: 30px;
			box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
			margin-bottom: 40px;
		}

		.section-title {
			font-size: 24px;
			margin-bottom: 20px;
			color: #2c3e50;
			border-bottom: 2px solid #f1f1f1;
			padding-bottom: 10px;
		}

		.review-form {
			background-color: #f8f9fa;
			padding: 20px;
			border-radius: 8px;
			margin-bottom: 30px;
		}

		.form-group {
			margin-bottom: 15px;
		}

		.form-group label {
			display: block;
			margin-bottom: 5px;
			font-weight: 500;
		}

		.form-group input,
		.form-group textarea,
		.form-group select {
			width: 100%;
			padding: 10px;
			border: 1px solid #ddd;
			border-radius: 5px;
			font-size: 16px;
		}

		.form-group textarea {
			min-height: 100px;
			resize: vertical;
		}

		.submit-button {
			background-color: #2ecc71;
			color: white;
			border: none;
			padding: 12px 25px;
			font-size: 16px;
			border-radius: 5px;
			cursor: pointer;
			transition: background-color 0.3s ease;
		}

		.submit-button:hover {
			background-color: #27ae60;
		}

		.reviews-list {
			display: flex;
			flex-direction: column;
			gap: 20px;
		}

		.review-item {
			border-bottom: 1px solid #f1f1f1;
			padding-bottom: 20px;
		}

		.review-header {
			display: flex;
			justify-content: space-between;
			margin-bottom: 10px;
		}

		.review-author {
			font-weight: bold;
			color: #2c3e50;
		}

		.review-date {
			color: #7f8c8d;
			font-size: 14px;
		}

		.review-rating {
			color: #f39c12;
			margin-bottom: 10px;
		}

		.review-text {
			color: #555;
		}

		footer {
			text-align: center;
			padding: 20px;
			color: #7f8c8d;
			border-top: 1px solid #eee;
			margin-top: 40px;
		}

		@media (max-width: 768px) {
			.product-section {
				flex-direction: column;
			}

			.product-image,
			.product-details {
				min-width: 100%;
			}
		}
	</style>
</head>

<body>
	<header>
		<div class="container">
			<div class="header-content">
				<div class="logo">МАГАЗИН</div>
				<nav>
					<a href="#" style="color: #3498db; text-decoration: none; margin-left: 15px;">Главная</a>
					<a href="#" style="color: #2c3e50; text-decoration: none; margin-left: 15px;">Каталог</a>
					<a href="#" style="color: #2c3e50; text-decoration: none; margin-left: 15px;">О нас</a>
					<a href="#" style="color: #2c3e50; text-decoration: none; margin-left: 15px;">Контакты</a>
				</nav>
			</div>
		</div>
	</header>

	<div class="container">
		<div class="product-section">
			<div class="product-image">
				<img src="https://via.placeholder.com/400x400" alt="Изображение товара">
            </div>

				<div class="product-details">
					<h1 class="product-title">кросовки ask</h1>

					<div class="price-section">
						<span class="original-price">4500 руб.</span>
						<span class="discount-price">3000 руб.</span>
						<span class="discount-badge">-33%</span>
					</div>

					<p>Высококачественнst кросовки из 100% хлопка. Идеально подходит для повседневной носки. Доступна в
						различных размерах.</p>

					<div class="size-section">
						<h3 class="size-title">Выберите размер:</h3>
						<div class="size-options">
							<div class="size-option" data-size="XS">XS</div>
							<div class="size-option" data-size="S">S</div>
							<div class="size-option selected" data-size="M">M</div>
							<div class="size-option" data-size="L">L</div>
							<div class="size-option" data-size="XL">XL</div>
						</div>
					</div>

					<button class="buy-button">Добавить в корзину</button>
				</div>
			</div>

			<div class="reviews-section">
				<h2 class="section-title">Отзывы о товаре</h2>

				<div class="review-form">
					<h3>Оставить отзыв</h3>
					<form id="reviewForm">
						<div class="form-group">
							<label for="reviewName">Ваше имя</label>
							<input type="text" id="reviewName" required>
                    </div>

							<div class="form-group">
								<label for="reviewRating">Оценка</label>
								<select id="reviewRating" required>
                            <option value="">Выберите оценку</option>
                            <option value="5">Отлично (5)</option>
                            <option value="4">Хорошо (4)</option>
                            <option value="3">Удовлетворительно (3)</option>
                            <option value="2">Плохо (2)</option>
                            <option value="1">Очень плохо (1)</option>
                        </select>
							</div>

							<div class="form-group">
								<label for="reviewText">Текст отзыва</label>
								<textarea id="reviewText" required></textarea>
							</div>

							<button type="submit" class="submit-button">Отправить отзыв</button>
					</form>
				</div>

				<div class="reviews-list" id="reviewsList">
					<div class="review-item">
						<div class="review-header">
							<span class="review-author">Анна Петрова</span>
							<span class="review-date">15.10.2023</span>
						</div>
						<div class="review-rating">★★★★★</div>
						<p class="review-text">Отличные кросовки! Качество ткани на высоте, размер соответствует. Очень
							довольна покупкой!</p>
					</div>

					<div class="review-item">
						<div class="review-header">
							<span class="review-author">Иван Сидоров</span>
							<span class="review-date">10.10.2023</span>
						</div>
						<div class="review-rating">★★★★☆</div>
						<p class="review-text">Хорошые кросовки за свои деньги. Немного пришли маловаты, но в целом
							рекомендую.</p>
					</div>
				</div>
			</div>
		</div>

		<footer>
			<div class="container">
				<p>© 2023 Магазин. Все права защищены.</p>
			</div>
		</footer>

		<script>
			// Выбор размера
        const sizeOptions = document.querySelectorAll('.size-option');
        sizeOptions.forEach(option => {
            option.addEventListener('click', function() {
                sizeOptions.forEach(opt => opt.classList.remove('selected'));
                this.classList.add('selected');
            });
        });
        
        // Обработка формы отзыва
        const reviewForm = document.getElementById('reviewForm');
        const reviewsList = document.getElementById('reviewsList');
        
        reviewForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('reviewName').value;
            const rating = document.getElementById('reviewRating').value;
            const text = document.getElementById('reviewText').value;
            
            if (name && rating && text) {
                // Создаем новый отзыв
                const reviewItem = document.createElement('div');
                reviewItem.className = 'review-item';
                
                // Форматируем дату
                const now = new Date();
                const dateStr = `${now.getDate().toString().padStart(2, '0')}.${(now.getMonth()+1).toString().padStart(2, '0')}.${now.getFullYear()}`;
                
                // Создаем звезды рейтинга
                let stars = '';
                for (let i = 0; i < 5; i++) {
                    stars += i < rating ? '★' : '☆';
                }
                
                reviewItem.innerHTML = `
                    <div class="review-header">
                        <span class="review-author">${name}</span>
                        <span class="review-date">${dateStr}</span>
                    </div>
                    <div class="review-rating">${stars}</div>
                    <p class="review-text">${text}</p>
                `;
                
                // Добавляем отзыв в начало списка
                reviewsList.prepend(reviewItem);
                
                // Очищаем форму
                reviewForm.reset();
                
                // Показываем сообщение об успехе
                alert('Спасибо за ваш отзыв!');
            }
        });
		</script>
</body>

</html>
