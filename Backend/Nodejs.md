# Nodejs

- Formidable

  > Get files from form-data

  ```javascript
  const form = new formidable.IncomingForm();
  form.parse(req, async (err, fields, files) => {}
  ```

* Debounce

  > Debounce search for 500 ms

  ```javascript
  const debounceSearch = _.debounce(getProductByKeyword, 500);

  const onChange = (e) => {
    e.persist();
    debounceSearch(e);
  };
  ```

## Courses

- [Node.js API Masterclass With Express & MongoDB](https://www.udemy.com/course/nodejs-api-masterclass)

  > Best Course so far for REST API Development with Node.js & Express

---

## Sendgrid

---
