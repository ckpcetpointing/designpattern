<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>OnLoad Custom Alert</title>

<style>
/* ===== Overlay ===== */
#customAlertOverlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.4);
    z-index: 9999;
}

/* ===== Alert Box ===== */
#customAlertBox {
    width: 360px;
    background: #fff;
    border-radius: 4px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-family: Arial, sans-serif;
}

/* ===== Title Bar ===== */
#customAlertTitle {
    background-color: #2f6fb2;
    color: #fff;
    padding: 10px 15px;
    font-size: 18px;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
}

/* ===== Message ===== */
#customAlertMessage {
    padding: 25px 15px;
    text-align: center;
    font-size: 15px;
    color: #000;
}

/* ===== Footer ===== */
#customAlertFooter {
    padding-bottom: 15px;
    text-align: center;
}

#customAlertFooter button {
    background-color: #2f6fb2;
    color: #fff;
    border: none;
    padding: 6px 25px;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
}
</style>
</head>

<body onload="initAlert()">

<h2>Other Page Content</h2>
<input type="text" placeholder="Unaffected component">

<!-- ===== ALERT HTML ===== -->
<div id="customAlertOverlay">
    <div id="customAlertBox">
        <div id="customAlertTitle"></div>
        <div id="customAlertMessage"></div>
        <div id="customAlertFooter">
            <button onclick="closeAlert()">OK</button>
        </div>
    </div>
</div>

<script>
/* These can come from JSP */
var status  = 'Oops!';
var message = 'Alert this pages';

/* JSP example:
var status  = '${status}';
var message = '${message}';
*/

function initAlert() {
    if (status && status.trim() !== '') {
        showAlert(status, message);
    }
}

function showAlert(title, msg) {
    document.getElementById("customAlertTitle").innerText = title;
    document.getElementById("customAlertMessage").innerText = msg;
    document.getElementById("customAlertOverlay").style.display = "block";
}

function closeAlert() {
    document.getElementById("customAlertOverlay").style.display = "none";
}
</script>

</body>
</html>
