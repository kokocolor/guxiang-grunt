1,全局安装 npm install -g grunt-cli

2,本地安装 npm install grunt --save-dev
3，安装grunt插件
cnpm install grunt-contrib-jshint   grunt-contrib-uglify  --save-dev
自动化
cnpm install grunt-contrib-watch  --save-dev

5，创建Gruntfile.js
module.exports = function(grunt) { // Project configuration. grunt.initConfig({ pkg: grunt.file.readJSON('package.json'), uglify: { options: { banner: '/*! <%= pkg.name %> <%= grunt.template.today("yyyy-mm-dd") %> */\n' }, build: { src: 'src/<%= pkg.name %>.js', dest: 'build/<%= pkg.name %>.min.js' } } }); // 加载包含 "uglify" 任务的插件。 grunt.loadNpmTasks('grunt-contrib-uglify'); // 默认被执行的任务列表。 grunt.registerTask('default', ['uglify']); };

6,执行命令grunt