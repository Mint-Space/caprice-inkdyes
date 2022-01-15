<template>
  <div class="submit">
    <div class="submit-info">
      <p>如果您有任何建议、商业合作，甚至想说声“Hello”,</p>
      <p>请填写下面的表格，我会尽快给您答复。</p>
    </div>
    <div class="submit-box">
      <div class="submit-input">
        <input type="text" name="" placeholder="姓名" />
        <input type="email" name="" placeholder="邮箱" />
      </div>
      <div class="submit-textarea">
        <textarea name="" placeholder="内容"></textarea>
      </div>
      <div class="submit-btn">
        <input type="submit" value="提交" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactSubmit",
};
</script>

<style lang="less" scoped>
.submit {
  display: flex;
  flex-flow: column;
  justify-content: space-between;
  align-items: flex-start;
  height: 80%;
  width: 55%;
  .submit-info {
    padding: 45px 0px;
    text-align: left;
    p {
      color: #555;
    }
  }
  .submit-box {
    width: 55%;
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    align-items: flex-start;
    padding: 10px 0px;
    height: 100%;
    .submit-input {
      height: 50px;
      border-radius: 25px;
      display: flex;
      flex-flow: row;
      justify-content: space-between;
      align-items: center;
      width: 100%;
      input {
        border-radius: 25px;
        padding: 12px 15px;
        // width: 40%;
        height: 80%;
        border: 1px solid #ccc;
        outline: none;
      }
    }
    .submit-textarea {
      height: 200px;
      width: 100%;
      textarea {
        border-radius: 25px;
        padding: 25px 15px;
        width: 100%;
        height: 80%;
        border: 1px solid #ccc;
        outline: none;
        box-sizing: border-box;
      }
    }
    .submit-btn {
      height: 50px;
      border-radius: 25px;
      input {
        border-radius: 25px;
        padding: 12px 0px;
        width: 150px;
        border: 1px solid #ccc;
        outline: none;
      }
    }
  }
}
</style>