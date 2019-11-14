# Upload image

[https://stackoverflow.com/questions/58785194/react-native-upload-image-to-firebase-storage/58848809\#58848809](https://stackoverflow.com/questions/58785194/react-native-upload-image-to-firebase-storage/58848809#58848809)  


1. If the file path looks like `file:///...`. You can just simple put it to Firebase function, don't need readFile step.

My code works properly up to now:

```javascript
  static uploadProfileAvatar(userID, fileURI) { // file URI is a path of a local image
    const updateTime = moment().unix();
    const storagePath = `${PROFILE_AVATAR_PATH}/${userID}_${updateTime}.jpg`;
    const fileMetaData = { contentType: 'image/jpeg' };
    return FirebaseStorage.uploadFile(fileURI, storagePath, fileMetaData);
  }

  static uploadFile(fileURI, storagePath, fileMetaData = null) {
    const uploadTask = firebase.storage().ref().child(storagePath).put(fileURI, fileMetaData);
    return uploadTask;
  }
```

1. If you have the path like `rct-image-store://0`. You have to write it to and then get the local path image.

```javascript
ImageStore.getBase64ForTag(
rctFileURI, // rct-image-store: path
(base64Image) => {
  const imagePath = `${RNFS.DocumentDirectoryPath}/${new Date().getTime()}.jpg`;
  RNFS.writeFile(imagePath, `${base64Image}`, 'base64')
  .then((success) => {
    // now your file path is imagePath (which is a real path)
    if (success) {
      // upload with imagePath, same as the 1
    }
  })
  .catch(() => {});
},
() => {},
);
```



