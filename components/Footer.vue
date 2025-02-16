<script lang="ts" setup>

</script>

<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-logo">
        <span>Мой Проект</span>
      </div>
      <nav class="footer-links">
        <ul>
          <li><a href="/about">О нас</a></li>
          <li><a href="/services">Услуги</a></li>
          <li><a href="/contacts">Контакты</a></li>
        </ul>
      </nav>
      <div class="footer-social">
        <a href="https://facebook.com" target="_blank" rel="noopener noreferrer">
          <img src="" alt="Facebook" />
        </a>
        <a href="https://twitter.com" target="_blank" rel="noopener noreferrer">
          <img src="" alt="Twitter" />
        </a>
        <a href="https://instagram.com" target="_blank" rel="noopener noreferrer">
          <img src="" alt="Instagram" />
        </a>
      </div>
      <div class="footer-copyright">
        &copy; 2025 Мой Проект. Все права защищены.
      </div>
    </div>
  </footer>
</template>

<style scoped lang="scss">
.footer {
  background-color: #2c3e50;
  color: #ecf0f1;
  padding: 20px 0;

  .footer-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;

    .footer-logo {
      display: flex;
      align-items: center;
      img {
        width: 40px;
        height: 40px;
        margin-right: 10px;
      }
      span {
        font-size: 1.2rem;
        font-weight: bold;
      }
    }

    .footer-links {
      ul {
        list-style: none;
        padding: 0;
        margin: 0;
        display: flex;
        gap: 15px;

        li {
          a {
            color: #ecf0f1;
            text-decoration: none;
            font-size: 0.9rem;
            transition: color 0.3s;
            &:hover {
              color: #3498db;
            }
          }
        }
      }
    }

    .footer-social {
      display: flex;
      gap: 10px;

      a {
        display: inline-block;
        img {
          width: 24px;
          height: 24px;
        }
        &:hover {
          opacity: 0.8;
        }
      }
    }

    .footer-copyright {
      text-align: center;
      font-size: 0.8rem;
      margin-top: 15px;
      width: 100%;
    }
  }
}
</style>