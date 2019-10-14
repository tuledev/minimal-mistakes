# Save Data with unique key

{% embed url="https://firebase.google.com/docs/database/admin/save-data" %}

### Save data with unique key

```text
var postsRef = ref.child("posts");

var newPostRef = postsRef.push();
newPostRef.set({
  author: "gracehop",
  title: "Announcing COBOL, a New Programming Language"
});

// we can also chain the two calls together
postsRef.push().set({
  author: "alanisawesome",
  title: "The Turing Machine"
});
```

```text

  "posts": {
    "-JRHTHaIs-jNPLXOQivY": {
      "author": "gracehop",
      "title": "Announcing COBOL, a New Programming Language"
    },
    "-JRHTHaKuITFIhnj02kE": {
      "author": "alanisawesome",
      "title": "The Turing Machine"
    }
  }
}
```

### Getting the unique key generated by push\(\)

```text
// Generate a reference to a new location and add some data using push()
var newPostRef = postsRef.push();

// Get the unique key generated by push()
var postId = newPostRef.key;
```
