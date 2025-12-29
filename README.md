<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <title>سفارش محصول</title>

    <style>
        body {
            font-family: sans-serif;
            background: #f5f5f5;
            text-align: center;
            padding-top: 50px;
        }

        .box {
            background: white;
            width: 300px;
            margin: auto;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 0 15px rgba(0,0,0,0.1);
        }

        button {
            background: #25d366;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 15px;
        }

        button:disabled {
            background: gray;
            cursor: not-allowed;
        }
    </style>
</head>

<body>

<div class="box">
    <h2>محصول ویژه</h2>
    <p id="stockText">موجودی: 3 عدد</p>

    <button id="orderBtn" onclick="orderProduct()">
        سفارش و تماس
    </button>
</div>

<script>
    let stock = 3;

    function orderProduct() {
        if (stock > 0) {
            stock--;
            document.getElementById("stockText").innerText =
                "موجودی: " + stock + " عدد";

            // تماس تلفنی
            window.location.href = "tel:09945881262";

            if (stock === 0) {
                document.getElementById("orderBtn").disabled = true;
                document.getElementById("stockText").innerText =
                    "موجودی: تمام شد ❌";
            }
        }
    }
</script>

</body>
</html>
