<template>
  <!-- vueに関する部分は
  ・各入力欄にv-modelをつける
  ・@click="checkForm"で送信ボタンの処理を結び付け
  ・checkFormでformDataのnameを出力する
  これらだけです

  ※デザインはCSSフレームワーク(bulma)を使用しています。 -->

  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>お問い合わせフォーム</title>

    <!-- CSSフレームワークを使う -->
    <!-- ・通常版 -->
    <!-- <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/bulma.min.css"> -->
    <!-- ・ライトテーマのみ版 -->
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/versions/bulma-no-dark-mode.css"
    />
  </head>
  <body>
    <div class="section">
      <div class="container">
        <form class="box" id="contactForm">
          <div class="field">
            <label class="label"
              >お名前
              <span style="color: red">*</span>
            </label>
            <div class="control">
              <input
                class="input"
                type="text"
                placeholder="田中 太郎"
                required
                v-model="formData.name"
              />
            </div>
          </div>
          <div class="field">
            <label class="label"
              >メールアドレス
              <span style="color: red">*</span>
            </label>
            <div class="control">
              <input
                class="input"
                type="email"
                placeholder="example@gmail.com"
                required
                v-model="formData.mailAddress"
              />
            </div>
          </div>
          <div class="field">
            <label class="label">電話番号</label>
            <div class="control">
              <input
                class="input"
                type="tel"
                placeholder="012-3456-7890"
                v-model="formData.phoneNumber"
              />
            </div>
          </div>
          <div class="field">
            <label class="label"
              >お問い合わせ内容
              <span style="color: red">*</span>
            </label>
            <div class="control">
              <div class="select">
                <select required v-model="formData.contentCD">
                  <option :value="0">製品について</option>
                  <option :value="1">商品について</option>
                  <option :value="2">なんとなく</option>
                </select>
              </div>
            </div>
          </div>
          <div class="field">
            <label class="label"
              >お問い合わせ詳細
              <span style="color: red">*</span>
            </label>
            <div class="control">
              <textarea
                class="textarea"
                cols="30"
                rows="5"
                placeholder="お問い合わせの詳細を記入してください"
                required
                v-model="formData.contentDetail"
              ></textarea>
            </div>
          </div>
          <div class="field">
            <label class="label"
              >送信前の確認
              <span style="color: red">*</span>
            </label>
            <div class="control">
              <label class="checkbox">
                <input
                  type="checkbox"
                  id="checkPrivacy"
                  v-model="formData.isConsent"
                />
                <a href="">プライバシーポリシー</a>
                に同意する
              </label>
            </div>
          </div>
          <div class="field">
            <label class="label"
              >もひとつ確認
              <span style="color: red">*</span>
            </label>
            <p class="help">
              ご回答までに最低でも1営業日ほどいただきますがよろしいでしょうか？
            </p>
            <div class="control">
              <label class="radio">
                <input
                  type="radio"
                  name="question"
                  v-model="formData.isAllowDelay"
                  :value="true"
                />
                Yes
              </label>
              <label class="radio">
                <input
                  type="radio"
                  name="question"
                  v-model="formData.isAllowDelay"
                  :value="false"
                  checked
                />
                No
              </label>
            </div>
          </div>
          <div class="buttons">
            <button class="button is-primary" @click="checkForm">
              送信する
            </button>
            <button class="button is-link is-light">Cancel</button>
          </div>
        </form>
      </div>
    </div>
  </body>
</template>

<script setup>
import { ref } from "vue";
const formData = ref({
  name: "",
  mailAddress: "",
  phoneNumber: "",
  contentCD: 0,
  contentDetail: "",
  isConsent: false,
  isAllowDelay: false,
});

function checkForm() {
  alert(formData.value.name);
}
</script>

<style scoped></style>
