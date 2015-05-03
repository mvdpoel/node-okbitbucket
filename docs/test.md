# TOC
   - [authentification](#authentification)
   - [email](#email)
   - [repo](#repo)
   - [ssh](#ssh)
   - [users](#users)
<a name=""></a>
 
<a name="authentification"></a>
# authentification
should authenticate using username and password.

```js
bitbucket.authenticatePassword(secrets.username, secrets.password);
bitbucket.getRepoApi().getUserRepos(secrets.username, function(err, repos) {
  (err == null).should.eql(true);
  repos.constructor.should.eql(Array);
  done();
});
```

<a name="email"></a>
# email
should get list of all email addresses.

```js
bitbucket.getEmailApi().getAll(function(err, emails) {
  (err == null).should.eql(true);
  emails.constructor.should.eql(Array);
  emails.length.should.be.above(0);
  emails[0].email.should.eql(secrets.email);
  done();
});
```

<a name="repo"></a>
# repo
should get user repos.

```js
bitbucket.getRepoApi().getUserRepos(secrets.username, function(err, repos) {
  (err == null).should.eql(true);
  repos.constructor.should.eql(Array);
  done();
});
```

should show extended user repository data.

```js
bitbucket.getRepoApi().show(secrets.username, 'test', function(err, repo) {
  (err == null).should.eql(true);
  ('owner' in repo).should.eql(true);
  repo.owner.should.eql(secrets.username);
  done();
});
```

<a name="ssh"></a>
# ssh
should delete/add ssh key.

```js
bitbucket.getSshApi().addKey(pubkey, function(err, key) {
  if (err) { console.error(err); }
  (err == null).should.eql(true);
  key.key.should.eql(pubkey);
  bitbucket.getSshApi().deleteKey(key.pk, function(err2){
    if (err2) { console.error(err2); }
    (err2 == null).should.eql(true);
    done();
  });
});
```

should prevent to overwrite existing keys.

```js
bitbucket.getSshApi().addKey(pubkey, function(err, key) {
  if (err) { console.error(err); }
  key.key.should.eql(pubkey);
  (err == null).should.eql(true);
  bitbucket.getSshApi().addKey(pubkey, function(err2) {
    if (err2) { console.error(err2); }
    err2.msg.should
      .match(/Someone has already registered that SSH key/);
    done();
  });
});
```

<a name="users"></a>
# users
should get data of authenticated user.

```js
bitbucket.getUserApi().get(function(err, data) {
  (err == null).should.eql(true);
  data.user.username.should.eql(secrets.username);
  ('repositories' in data).should.eql(true);
  done();
});
```

should get repositories of authenticated user.

```js
bitbucket.getUserApi().getRepositories(function(err, data) {
  (err == null).should.eql(true);
  (data.constructor).should.be.eql(Array);
  done();
});
```

<a name="users"></a>
# users
should get data of authenticated user.

```js
bitbucket.getUsersApi().getUserData(secrets.username, function(err, data) {
  (err == null).should.eql(true);
  data.user.username.should.eql(secrets.username);
  ('repositories' in data).should.eql(true);
  done();
});
```

