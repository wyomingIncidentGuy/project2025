<script lang="ts" setup>

</script>

<template>
  <header class="header">
    <div class="header-container">
      <div class="header-logo">
        <a href="/">Мой Проект</a>
      </div>
      <nav class="header-nav">
        <ul>
          <li><a href="/about">О нас</a></li>
          <li><a href="/services">Услуги</a></li>
          <li><a href="/contacts">Контакты</a></li>
        </ul>
      </nav>
      <div class="header-actions">
        <button>Войти</button>
      </div>
    </div>
  </header>
</template>

<style scoped lang="scss">
.header {
  background-color: #2c3e50;
  color: #ecf0f1;
  padding: 15px 0;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

  .header-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;

    @media screen and (max-width: 1220px) {
        max-width: none;
        width: calc(100% - 40px);
        padding: 0 20px;
    }

    .header-logo {
      a {
        color: #ecf0f1;
        font-size: 1.5rem;
        font-weight: bold;
        text-decoration: none;
        transition: color 0.3s;

        &:hover {
          color: #3498db;
        }
      }
    }

    .header-nav {
      ul {
        list-style: none;
        display: flex;
        gap: 20px;
        padding: 0;
        margin: 0;

        li {
          a {
            color: #ecf0f1;
            text-decoration: none;
            font-size: 1rem;
            transition: color 0.3s;

            &:hover {
              color: #3498db;
            }
          }
        }
      }
    }

    .header-actions {
      button {
        background-color: #3498db;
        color: #fff;
        border: none;
        border-radius: 4px;
        padding: 8px 15px;
        font-size: 0.9rem;
        cursor: pointer;
        transition: background-color 0.3s;

        &:hover {
          background-color: #1d6fa5;
        }
      }
    }
  }
}
</style>