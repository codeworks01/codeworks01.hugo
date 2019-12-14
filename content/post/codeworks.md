+++
authors = [""]
date = 2019-12-14T05:00:00Z
excerpt = "DevSecOps"
hero = "/uploads/-76543ew21q.png"
timeToRead = 5
title = "Codeworks"

+++
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

>     var createError = require('http-errors');
>     var express = require('express');
>     var path = require('path');
>     var cookieParser = require('cookie-parser');
>     var logger = require('morgan');
>     
>     var indexRouter = require('./routes/index');
>     var usersRouter = require('./routes/users');
>     var k8Router = require('./routes/k8');
>     
>     var app = express();
>     
>     // view engine setup
>     app.set('views', path.join(__dirname, 'views'));
>     app.set('view engine', 'pug');
>     
>     app.use(logger('dev'));
>     app.use(express.json());
>     app.use(express.urlencoded({ extended: false }));
>     app.use(cookieParser());
>     app.use(express.static(path.join(__dirname, 'public')));
>     
>     app.use('/', indexRouter);
>     app.use('/users', usersRouter);
>     app.use('/k8', k8Router);
>     
>     // catch 404 and forward to error handler
>     app.use(function(req, res, next) {
>       next(createError(404));
>     });
>     
>     // error handler
>     app.use(function(err, req, res, next) {
>       // set locals, only providing error in development
>       res.locals.message = err.message;
>       res.locals.error = req.app.get('env') === 'development' ? err : {};
>     
>       // render the error page
>       res.status(err.status || 500);
>       res.render('error');
>     });
>     
>     module.exports = app;	