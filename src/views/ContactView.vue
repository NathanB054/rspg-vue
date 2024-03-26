<template>
  <div class="contacts testbox">
      <form action="/">
        <h2 class="cont">ติดต่อเรา</h2>
        <div class="item">
          <p>Name</p>
          <div class="name-item">
            <input type="text" name="name" placeholder="First" />
            <input type="text" name="name" placeholder="Last" />
          </div>
        </div>
        <div class="item">
          <div class="item">
            <p>Email</p>
            <input type="text" name="name" placeholder="Email"/>
          </div>
        </div>
        <div class="item">
          <p>Details</p>
          <textarea rows="3" required placeholder="Please write details here..."></textarea>
        </div>
        <div class="btn-block">
          <button type="submit" href="/">APPLY</button>
        </div>
      </form>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style  scoped>
.contacts{
    height: 65vh;
    text-align: center;
}
.cont{
    font-size: 30px;
    font-weight: 700;
    color: #b22160;
}
.email{
    text-align: end;
}
body, div, form, input, textarea, p { 
      padding: 0;
      margin: 0;
      outline: none;
      font-size: 14px;
      color: #390f65;
      line-height: 22px;
      }
      h1 {
      position: absolute;
      margin: 0;
      font-size: 32px;
      color: #fff;
      z-index: 2;
      }
      .testbox {
      display: flex;
      justify-content: center;
      align-items: center;
      height: inherit;
      padding: 20px;
      }
      form {
        height: 65vh;
      width: 80%;
      padding: 20px;
      border-radius: 6px;
      background: #fff;
      box-shadow: 0 0 10px 0 #cc0052; 
      }
      input, textarea {
      margin-bottom: 10px;
      border-radius: 10px;
      background-color: #efdcef;
      }
      input {
      width: calc(100% - 10px);
      padding: 5px;
      }
      textarea {
      width: calc(100% - 12px);
      padding: 5px;
      }
      .item:hover p, input:hover::placeholder {
      color: #b81cdf;
      }
      .item input:hover, .item textarea:hover {
      border: 1px solid transparent;
      box-shadow: 0 0 6px 0 #b81cdf;
      color: #b81cdf;
      }
      .item {
      position: relative;
      margin: 10px 0;
      }
      .btn-block {
      margin-top: 10px;
      text-align: center;
      }
      button {
      width: 150px;
      padding: 10px;
      border: none;
      border-radius: 5px; 
      background: #cc0052;
      font-size: 16px;
      color: #fff;
      cursor: pointer;
      }
      button:hover {
      background: #ff0066;
      }
      @media (min-width: 568px) {
      .name-item, .contact-item {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      }
      .contact-item .item {
      width: calc(50% - 8px);
      }
      .name-item input {
      width: calc(50% - 20px);
      }
      .contact-item input {
      width: calc(203% - 12px);
      }
      }
</style>