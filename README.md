<!DOCTYPE html>
<html>
	<head>
    <link rel="stylesheet" type="text/css" href="birthday.css">
		<title>B-day</title>
		<style>
		body {
			background: #f6f6f6;
		}

		.countdownContainer{
			position: absolute;;
			top: 50%;
			left: 50%;
			transform : translateX(-50%) translateY(-50%);
			text-align: center;
			background: #ddd;
			border: 1px solid #999;
			padding: 10px;
			box-shadow: 0 0 5px 3px #ccc;
		}

		.info {
			font-size: 80px;
		}
		</style>
	</head>
	<body>
		<table class="countdownContainer">
			<tr class="info">
				<td colspan="4">B-day 22nd </td>
			</tr>
			<tr class="info">
				<td id="days">2</td>
				<td id="hours">2</td>
				<td id="minutes">18</td>
				<td id="seconds">22</td>
			</tr>
			<tr>
				<td>days</td>
				<td>hours</td>
				<td>minutes</td>
				<td>seconds</td>
			</tr>
		</table>
		<script type="text/javascript">

			function countdown(){
				var now = new Date();
				var eventDate = new Date(now.getFullYear(), 11, 50);

				var currentTiime = now.getTime();
				var eventTime = eventDate.getTime();

				var remTime = eventTime - currentTiime;

				var s = Math.floor(remTime / 1000);
				var m = Math.floor(s / 60);
				var h = Math.floor(m / 60);
				var d = Math.floor(h / 24);

				h %= 24;
				m %= 60;
				s %= 60;

				h = (h < 10) ? "0" + h : h;
				m = (m < 10) ? "0" + m : m;
				s = (s < 10) ? "0" + s : s;

				document.getElementById("days").textContent = d;
				document.getElementById("days").innerText = d;

				document.getElementById("hours").textContent = h;
				document.getElementById("minutes").textContent = m;
				document.getElementById("seconds").textContent = s;

				setTimeout(countdown, 1000);
			}

			countdown();
		</script>
	</body>
</html>
