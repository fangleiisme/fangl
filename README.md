<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Do you miss me?</title>
    <style>
        html, body {
            margin: 0;
            padding: 0;
            background: #f2f1f6;
        }
        .container {
            position: relative;
            width: 500px;
            height: 300px;
            background: #f2f1f6;

        }
        .container h1 {
            margin-top: 0;
            text-align: center;
        }
        .container img {
            vertical-align: -70px;
        }
        .bd {
            padding-left: 30px;
        }
        .ft {
            position: absolute;
            width: 100%;
            bottom: 20px;
            padding: 0 30px;
            line-height: 30px;
            box-sizing: border-box;
        }
        .btn-group {
            float: left;
        }
        .fr {
            float: right;
        }
        button {
            cursor: pointer;
        }
        #p1 {
        }
        .not-allow {
            position: relative;
        }
        #p2 {
            display: none;
        }
        #p3 {
            display: none;
        }
        .red {
            margin: 0;
            font-size: 24px;
            padding: 30px 40px;
            color: red;
            letter-spacing: 4px;
        }
        .wavy {
            text-decoration: underline;
            text-decoration-style: wavy;
        }
        .name {
            padding-left: 10px;
        }
        .btn {
            padding: 6px 12px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div id="p1">
            <h1>小姐姐</h1>
            <div class="bd">
                想我了吗???
            </div>

            <div class="ft">
                <div class="btn-group">
                    <button class="btn allow">想</button>
                    <button class="btn not-allow" id="not-allow">不想</button>
                </div>
                <!-- <div class="fr">
                    辞职人: <span class="name">小姐姐</span>
                </div> -->
            </div>
        </div>
        <div id="p2">
            <h2 class="red">
                想就对了嘛！！！
            </h2>
            <div class="ft">
                <button class="btn allow2">退出</button>
            </div>
        </div>
        <div id="p3">
            <h1>再问一遍!!!!!</h1>
            <div class="bd">
                小姐姐, 想我了吗???
            </div>

            <div class="ft">
                <div class="btn-group">
                    <button class="btn allow3">想</button>
                    <button class="btn not-allow" id="not-allow2">不想</button>
                </div>
                <!-- <div class="fr">
                    辞职人: <span class="name">小姐姐</span>
                </div> -->
            </div>
        </div>
    </div>

    <script>
        (function(){
            function $(selector) {
                return document.querySelector(selector);
            }
            var $p1 = document.getElementById('p1');
            var $p2 = document.getElementById('p2');
            var $p3 = document.getElementById('p3');
            var $container = $('.container');
            var $btn = $('#not-allow');
            var $btn2 = $('#not-allow2');
            var isBlockClose = true;

            var maxX = $container.clientWidth - 1, maxY = $container.clientHeight - 1;
            var originPos = $btn.getBoundingClientRect();

            $('.allow').addEventListener('click', function() {
                $p1.style.display = 'none';
                $p2.style.display = 'block';
                $p3.style.display = 'none';
            });
            $('.allow2').addEventListener('click', function() {
                $p1.style.display = 'none';
                $p2.style.display = 'none';
                $p3.style.display = 'block';
            });
            $('.allow3').addEventListener('click', function() {
                $p1.style.display = 'none';
                $p2.style.display = 'block';
                $p3.style.display = 'none';
            });
            $btn.addEventListener('mouseover', function() {
                this.style.left = Math.floor(Math.random() * maxX - originPos.left) + 'px';
                this.style.top = Math.floor(Math.random() * maxY - originPos.top) + 'px';
                //console.log(this.style.left, this.style.top);
            });
            $btn2.addEventListener('mouseover', function() {
                this.style.left = Math.floor(Math.random() * maxX - originPos.left) + 'px';
                this.style.top = Math.floor(Math.random() * maxY - originPos.top) + 'px';
                //console.log(this.style.left, this.style.top);
            });
            $('.exit').addEventListener('click', function() {
                isBlockClose = false;
                window.close();
            });
            window.addEventListener('beforeunload', function(e) {
                if (isBlockClose) {
                    alert("此路不通");
                    e.returnValue = false;
                    e.preventDefault();
                    return "此路不通";
                }
            });
        })();
    </script>
</body>
</html>
