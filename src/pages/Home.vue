<template>
  <h1>Welcome to the Forum</h1>
  <CategoryList :categories="categories"/>
</template>

<script>
import CategoryList from '@/components/CategoryList'
import sourceData from '@/data.json'
export default {
  components: {
    CategoryList
  },
  data () {
    return {
      categories: sourceData.categories
    }
  }
}
</script>

<style>
.post-list {
    margin-top: 20px;
}

.post {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    background-color: white;
    padding: 20px 10px;
    padding-bottom: 7px;
    box-shadow: 2px 2px 1px rgba(136, 136, 136, 0.09);
    margin-bottom: 20px;
}

@media (max-width: 820px) {
    .post {
        padding: 0;
    }
}

.post .user-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    text-align: center;
    flex: 1 1 15%;
    margin-right: 5px;
}

.post .user-info > * {
    margin-bottom: 10px;
}

@media (max-width: 820px) {
    .post .user-info {
        order: -2;
        flex-direction: row;
        justify-content: flex-start;
        background: rgba(73, 89, 96, 0.06);
        margin-right: 0;
        padding: 5px;
        padding-left: 10px;
    }

    .post .user-info .avatar-large {
        height: 35px;
        width: 35px;
        margin-right: 5px;
        order: 1;
    }

    .post .user-info .user-name {
        order: 2;
    }

    .post .user-info > * {
        margin-right: 5px;
        margin-bottom: 0;
    }
}

.post .post-date {
    flex-basis: 100%;
    font-size: 14px;
    text-align: right;
    margin-bottom: 5px;
    padding-right: 7px;
}

@media (max-width: 820px) {
    .post .post-date {
        order: -1;
        flex-basis: 40%;
        background: rgba(73, 89, 96, 0.06);
        padding-right: 10px;
        padding-top: 16px;
        margin-bottom: 0px;
    }
}

@media (max-width: 720px) {
    .post {
        padding: 0px;
    }
}

.post-content {
    display: flex;
    flex: 1 0 83%;
    padding-left: 15px;
    padding-right: 10px;
    font-size: 16px;
    text-align: justify;
    line-height: 1.5;
    word-break: break-word;
}

.post-content h1, .post-content h2, .post-content h3 {
    margin-bottom: 0;
}

.post-content p {
    margin-bottom: 20px;
}

.post-content pre {
    display: grid;
    overflow: auto;
    word-wrap: break-word;
    border-radius: 3px;
    padding: 10px;
}

.post-content blockquote {
    margin: 25px 0px;
}

.post-content blockquote.big {
    display: flex;
    position: relative;
}

.post-content blockquote.big::before {
    position: absolute;
    top: -25px;
    left: -25px;
    font-size: 42px;
    font-family: FontAwesome;
    content: "\f10e";
    color: #263959;
}

@media (max-width: 820px) {
    .post-content blockquote.big::before {
        top: -15px;
        left: -18px;
        font-size: 32px;
    }
}

.post-content blockquote.big .quote {
    padding-left: 20px;
    padding-right: 15px;
    flex-basis: 95%;
    font-weight: 100;
    font-style: italic;
    font-size: 17px;
}

.post-content blockquote.big .author {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    text-align: center;
}

.post-content blockquote.big .author img {
    flex: 1;
    flex-basis: 100%;
    margin-top: 10px;
    width: 80px;
    height: 80px;
}

.post-content blockquote.small {
    /* display: flex; */
    position: relative;
    flex-direction: column;
    border: 2px solid rgba(152, 152, 152, 0.15);
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
}

.post-content blockquote.small::before {
    position: absolute;
    top: -20px;
    left: -20px;
    font-size: 42px;
    font-family: FontAwesome;
    content: "\f10e";
    color: #263959;
}

@media (max-width: 820px) {
    .post-content blockquote.small::before {
        top: -18px;
        left: -15px;
        font-size: 32px;
    }
}

.post-content blockquote.small .author {
    display: flex;
    flex-basis: 100%;
    padding: 3px 10px 3px 28px;
    background-color: rgba(152, 152, 152, 0.15);
    justify-content: center;
    align-items: center;
}

.post-content blockquote.small .author .time {
    margin-left: 10px;
}

.post-content blockquote.small .author .fa {
    margin-left: auto;
    font-size: 20px;
}

.post-content blockquote.small .author .fa:hover {
    cursor: pointer;
}

.post-content blockquote.small .quote {
    display: flex;
    flex-basis: 100%;
    flex-direction: column;
    padding: 10px;
    font-weight: 100;
    font-style: italic;
    font-size: 17px;
}

.post-content blockquote.simple {
    position: relative;
    padding: 0px 10px 0px 20px;
    font-weight: 100;
    font-style: italic;
    font-size: 17px;
    letter-spacing: .15px;
}

.post-content blockquote.simple::before {
    position: absolute;
    top: -25px;
    left: -25px;
    font-size: 42px;
    font-family: FontAwesome;
    content: "\f10e";
    color: #263959;
}

@media (max-width: 820px) {
    .post-content blockquote.simple::before {
        top: -15px;
        left: -18px;
        font-size: 32px;
    }
}

.post-content blockquote.simple .author {
    display: block;
    margin-top: 10px;
    font-weight: normal;
}

.post-content blockquote.simple .author .time {
    margin-left: 10px;
}

.post-listing-editor {
    flex: 1 1 83%;
}
</style>
