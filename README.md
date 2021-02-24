# infinite-scroll-blog 만들기 (1)
## css, javascript


![image](https://user-images.githubusercontent.com/71425369/108979586-27eb3a80-76ce-11eb-9251-884ade65d043.png)

---

1️⃣ `posting list` css & javascript 기능 구현

javascript를 통해 `post` 부분을 생성해준다

`javascript`
```js
// Show posts in DOM
async function showPosts() {
    const posts = await getPosts();

    posts.forEach((post) => {
        const postEl = document.createElement("div");
        postEl.classList.add("post");
        postEl.innerHTML = `
      <div class="number">${post.id}</div>
      <div class="post-info">
        <h2 class="post-title">${post.title}</h2>
        <p class="post-body">${post.body}</p>
      </div>
    `;

        postsContainer.appendChild(postEl);
    });
}
```

`css`
```css
.post {
    position: relative;
    background-color: #084126;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
    border-radius: 3px;
    padding: 20px;
    margin: 40px 0;
    display: flex;
    width: 80vw;
    max-width: 800px;
}

.post .post-title {
    margin: 0;
}

.post .post-body {
    margin: 15px 0 0;
    line-height: 1.3;
}

.post .post-info {
    margin-left: 20px;
}

.post .number {
    position: absolute;
    top: -15px;
    left: -15px;
    font-size: 15px;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: #fff;
    color: #296ca8;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 7px 10px;
}
```
