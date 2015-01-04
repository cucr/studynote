+---
title: Avalon探索之旅
layout: page
category: avalon
date: 2014-12-30
modifiedOn: 2014-12-30
---

## jquery angularJS avalon实现todolist

### jquery
HTML代码
{% highlight html %}
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>todo list</title>
        <link rel="stylesheet" href="../style/bootstrap.css">
    </head>
    <body>
        <div class="container">
            <div class="row">
                <div class="col-md-5">
                    <form action="" id="todoForm">
                        <label for="">将下面的输入放入todo list！</label>
                        <input type="text" id="todoInput" class="formcontrol">
                    </form>
                    <p id="todoCount"></p>
                    <ol id="todoList"></ol>
                </div>
            </div>
        </div>  
        <script src="../js/jquery-1.10.2.js"></script>
        <script src="./todojquery.js"></script> 
    </body>
    </html>
{% highlight html %}

JS代码
{% highlight javascript %}
    (function(){
        var $todoForm = $('#todoForm');
        var $todoInput = $('#todoInput');
        var $todoList = $('#todoList');
        var $todoCount = $('#todoCount');

        function count(){
            var len = $todoList.children().length;
            $todoCount.html(len>0?'共'+len+'项todo list':'');
        }

        //回车提交
        $todoForm.submit(function(e) {
            var input_value = $todoInput.val();
            $todoList.append('<li>'+input_value+'&nbsp;<a href="#" class="todoDelete">x</a></li>');
            $todoInput.val('');
            count();
            //阻止页面会重新刷新
            return false;
        });

        //绑定删除
        $todoList.on('click','.todoDelete',function(e){
            $(this).parent().remove();
        })

    })();
{% highlight javascript %}

### angular

### avalon
实现MVVM，同时相比angular学习成本更低，代码编写更易



