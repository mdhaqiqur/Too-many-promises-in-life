# Too-many-promises-in-life
function createPost(postData) {
  // createPost logic
  // returns a promise
}

function updateLastUserActivityTime(userId) {
  // updateLastUserActivityTime logic
  // returns a promise
}

function deletePost(postId) {
  // deletePost logic
  // returns a promise
}

function getAllPosts(userId) {
  // getAllPosts logic
  // returns a promise
}

function createAndDeletePost(userId, postData) {
  createPost(postData)
    .then(() => updateLastUserActivityTime(userId))
    .then(() => getAllPosts(userId))
    .then(posts => {
      console.log(posts);
      return deletePost(posts[posts.length - 1].id);
    })
    .then(() => getAllPosts(userId))
    .then(posts => {
      console.log(posts);
    })
    .catch(error => console.log(error));
}
