# Set up Firebase realtime database

I'm using [FBRD](https://firebase.google.com/docs/database?hl=en) because I'm not storing much data, the data is relatively flat, and I will be doing a lot of small read/writes. Firestore charges per read/write and can't use more than one database in free tier anyway.

[Instructions for setup](https://firebase.google.com/docs/database/web/start?hl=en)

- URL for db will be DATABASE_NAME.firebaseio.com (for databases in us-central1)
