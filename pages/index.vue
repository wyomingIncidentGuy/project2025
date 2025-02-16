<script lang="ts" setup>

</script>

<template>
    <main class="container">
        <section class="hero">
            <h1>Добро пожаловать на платформу для публикации проектов!</h1>
            <p>Здесь вы можете загружать свои проекты, делиться ими с сообществом и получать отзывы.</p>
        </section>

        <section class="features">
            <h2>Почему стоит выбрать нас?</h2>
            <div class="feature-list">
                <div class="feature">
                    <h3>✅ Легкость использования</h3>
                    <p>Простая и интуитивно понятная система загрузки проектов.</p>
                </div>
                <div class="feature">
                    <h3>🚀 Быстрая публикация</h3>
                    <p>Ваши проекты становятся доступными моментально.</p>
                </div>
                <div class="feature">
                    <h3>💬 Обратная связь</h3>
                    <p>Получайте комментарии и советы от других разработчиков.</p>
                </div>
                <div class="feature">
                    <h3>🔒 Безопасность</h3>
                    <p>Ваши данные защищены с помощью современных технологий.</p>
                </div>
            </div>
        </section>

        <section class="how-it-works">
            <h2>Как это работает?</h2>
            <ol>
                <li>Создайте аккаунт и войдите в систему.</li>
                <li>Перейдите в раздел "Загрузить проект".</li>
                <li>Заполните информацию о проекте (название, описание, технологии).</li>
                <li>Загрузите файлы проекта или укажите ссылку на репозиторий.</li>
                <li>Опубликуйте проект и делитесь им с сообществом!</li>
            </ol>
        </section>
    </main>
</template>

<style lang="scss" scoped>
    main{
        display: flex;
        gap: 30px;
    }

    .hero {
    text-align: center;
    max-width: 800px;
    background: #fff;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);

    h1 {
        font-size: 28px;
        color: #333;
        margin-bottom: 15px;
    }

    p {
        font-size: 18px;
        color: #666;
        margin-bottom: 20px;
    }
}

.features {
    max-width: 900px;
    text-align: center;

    h2 {
        font-size: 24px;
        color: #333;
        margin-bottom: 20px;
    }

    .feature-list {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 20px;
    }

    .feature {
        background: #fff;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);

        h3 {
            font-size: 20px;
            color: #007bff;
            margin-bottom: 10px;
        }

        p {
            font-size: 16px;
            color: #666;
        }
    }
}

.how-it-works {
    max-width: 800px;
    text-align: left;
    background: #fff;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);

    h2 {
        font-size: 24px;
        color: #333;
        margin-bottom: 15px;
    }

    ol {
        font-size: 18px;
        color: #666;
        padding-left: 20px;

        li {
            margin-bottom: 10px;
        }
    }
}
</style>