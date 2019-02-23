---
title: "Use try-catch exception rather than return codes, and async/await rather than then/catch for Promises in JavaScript"
categories:
  - JavaScript
tags:
  - JavaScript
  - try-catch
  - async/await
---

In a few weeks ago, I rarely used `try-catch`. But after I read [Clean Code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) again, I realised something and used try-catch more frequently.

Let's consider a scenario: a program has an user's information screen with **usename**, **avatar** field. After user changed [username, avatar], then press **UPDATE** button. The program will do: 

 1. Validate username (longer than 5 characters).
 2. Show loading animation 
 3. Upload avatar to an image server.
 4. Update user's info: username, avatar.
 5. Show Success alert, hide loading animation, .
 6. Hide loading animation if fail at any point.

Go with these codes (just focus on `validateUsername` and `onUpdateButtonPressed` function):

```javascript
  const MIN_USERNAME_LENGTH = 6;
  const ERROR_TYPE = {
    NONE: 'NONE',
    NULL_USERNAME: 'NULL_USERNAME',
    SHORT_USERNAME: 'SHORT_USERNAME',
    UPLOAD_AVATAR: 'UPLOAD_AVATAR',
    UPDATE_INFO: 'UPDATE_INFO',
  }

  const SUCCESSFUL_UPDATED = 'Niceeee!';
  const NULL_USERNAME = 'Username can not be null';
  const SHORT_USERNAME = 'You are too short!';
  const FAIL_UPLOAD_AVATAR = 'Uploading avartar failed';
  const FAIL_UPDATE_INFO = 'Updating info failed';

  functions showAlert(contentText) {
    // show alert with contentText
  }

  function showSuccessAlert() {
    showAlert(SUCCESSFUL_UPDATED);
  }

  function showFailAlert(failText) {
    showAlert(failText);
  }

  function showLoading() {
    // show loading animation
  }

  function hideLoading() {
    // hide loading animation
  }

  function uploadImages(imagePath) {
    return new Promise((resolve, reject) => {
      Client.uploadImage(
        imagePath,
        () => { reject(ERROR_TYPE.UPLOAD_AVATAR); }, // error
        (url) => { resolve(url); }, // success
      );
    });
  }

  function updateUserInfo(username, avatarUrl) {
    return new Promise((resolve, reject) => {
      Client.updateUserInfo(
        username,
        avatarUrl,
        () => { reject(ERROR_TYPE.UPDATE_INFO); }, // error
        () => { resolve(); }, // success
      );
    });
  }

  function validateUsername(username) {
    if (!username) { 
      return ERROR_TYPE.NULL_USERNAME;
    }
    else if (username.length < MIN_USERNAME_LENGTH) {
      return ERROR_TYPE.SHORT_USERNAME;
    }
    return ERROR_TYPE.NONE;
  }

  function onUpdateButtonPressed(username, avatarPath) {

    // 1. validate username
    const resultValidateUsername = validateUsername(username);
    if (resultValidateUsername === ERROR_TYPE.NULL_USERNAME) {
      showFailAlert(NULL_USERNAME);
      return;
    }
    if (resultValidateUsername === ERROR_TYPE.SHORT_USERNAME) {
      showFailAlert(SHORT_USERNAME);
      return;
    }

    // 2. Show loading animation 
    showLoading();

    // 3. upload avatar
    uploadImages(avatarPath)
      .then(avatarUrl => {

        // 4. update user's info
        return updateUserInfo(username, avatarUrl);
      })
      .then(() => {

        // 5. hide loading and show success alert
        showSuccessAlert();
        hideLoading();
      })
      .catch((err) => {
        // 6. hide loading if failed
        hideLoading();

        if (err === ERROR_TYPE.UPLOAD_AVATAR) {
          showFailAlert(FAIL_UPLOAD_AVATAR);
        }
        else if (err === ERROR_TYPE.UPDATE_INFO){
          showFailAlert(FAIL_UPDATE_INFO);
        }
      });
  }

```

We can smell something in the `onUpdateButtonPressed` function:
- 2 `return` lines(better than nested if)
- chaining Promises(better than nested Promises)
- a little complex show/hide loading flow
- hard to figure out the updating flow

It's not bad at all. But imagine, if we have more error codes and chaining Promises, the code will be massive and hard to be maintained.

So let's refactor `onUpdateButtonPressed` with `try-catch` and `async/await`

```javascript
  function validateUsername(username) {
    if (!username) { 
      throw ERROR_TYPE.NULL_USERNAME;
    }
    else if (username.length < MIN_USERNAME_LENGTH) {
      throw ERROR_TYPE.SHORT_USERNAME;
    }
  }

  async function onUpdateButtonPressed(username, avatarPath) {
    try {
      validateUsername(username);
      showLoading();
      const avatarUrl = await uploadImages(avatarPath);
      await updateUserInfo(username, avatarUrl);
      showSuccessAlert();
    }
    catch (err) {
      handleError(err);
    }
    finally {
      hideLoading();
    }
  }

  function handleError(err) {
    switch (err) {
      case ERROR_TYPE.NULL_USERNAME: 
        showFailAlert(NULL_USERNAME);
        break;
      case ERROR_TYPE.SHORT_USERNAME: 
        showFailAlert(SHORT_USERNAME);
        break;
      case ERROR_TYPE.UPLOAD_AVATAR: 
        showFailAlert(FAIL_UPLOAD_AVATAR);
        break;
      case ERROR_TYPE.UPDATE_INFO: 
        showFailAlert(FAIL_UPLOAD_AVATAR);
        break;
      default:
      break;
    }
  }
```

What I did:
- In `validateUsername`, instead of return error codes, `throw` them.
- In `onUpdateButtonPressed`, instead of using `then/catch` with Promises, using `try-catch` and `async/await`.

I think the code is good now:
- We can easy understand the flow line by line: validateUsername -> showLoading -> uploadImages -> updateUserInfo -> showSuccessAlert
- Errors are handled in one place `handleError`.

From now, I always try to use `try-catch-finally` first for cases as this scenario.

More detail about [try-catch](https://javascript.info/try-catch)

<br>

**HAPPY CODING!**

