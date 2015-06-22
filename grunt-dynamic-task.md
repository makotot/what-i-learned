# Grunt dynamic task

`serve`タスクと`build`タスクでパスを変更したい時とか。

```js
grunt.initConfig({
  path: {
    src: './src',
    env: './dev'
  }
});
```


`grunt.config.set()`or`grunt.config()`でconfigを変更してタスクを実行する。

```js

grunt.registerTask('build', 'build task', function () {
  grunt.config.set('path.env', './build');

  grunt.task.run(['...']);
});
```

## Links

- [Grunt Tricks: Part One | dontkry.com](http://dontkry.com/posts/code/grunt-tricks.html)

