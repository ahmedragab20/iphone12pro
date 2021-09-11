<template>
  <footer class="mt-5">
    <div class="container">
      <div class="row">
        <div class="col-lg-6">
          <div class="headline">
            <h3>iphone 12 pro</h3>
            <p>Created by Ahmed Ragab &copy; 2021</p>
          </div>
        </div>
        <div class="col-lg-6">
          <ul class="links">
            <li>Home</li>
            <li>Store</li>
            <li>More</li>
            <li class="top">
              <a href="#"> Top<i class="bi bi-arrow-up"></i></a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>
<style lang="scss" scoped>
footer {
  padding: 10px 0;
  background: #16161746;

  .headline {
    h3 {
      /*background: linear-gradient(to right, #005e7f, #61b6cd);
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;*/
      font-size: 1.2rem;
      font-weight: 600;
      text-transform: uppercase;
      cursor: pointer;
    }
    p {
      font-size: 0.75rem;
    }
  }

  .links {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 10px;

    li {
      cursor: pointer;
      padding: 3px 10px;
      border-radius: 20px;
      transition: all 0.3s ease;

      &:hover {
        background-color: #fff;
        color: #000;
      }
    }
    .top {
      background-color: #fff;
      font-weight: 600;
      transition: all 0.3s ease-in-out;
      padding: 0;
      width: 80px;
      height: 30px;

      &:hover {
        background-color: rgb(216, 216, 216);
      }

      * {
        color: #000;
        text-decoration: none;
      }
      a {
        width: 100%;
        height: 100%;
        text-align: center;
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }
  }
}

@media (max-width: 768px) {
  footer {
    text-align: center;
    .links {
      justify-content: center;
      font-size: 0.75rem;
      transform: translateX(-20px);
    }
  }
}
</style>
