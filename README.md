<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Countdown Timer</title>
    <style>
        body {
            font-family: 'Monaco', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-image: url('https://imgur.com/gEn7uWN.jpg'); /* Background image */
            background-size: cover;
            background-position: center;
            margin: 0;
            flex-direction: column;
            color: #333;
        }

        .countdown-container {
            text-align: center;
           
            

        .countdown-container h1 {
            font-size: 30px;
            margin-bottom: 30px;
           
            color: #333; /* Dark text for better visibility */
        }

        .countdown {
            display: flex;
            justify-content: space-around;
           
        }

        .time-unit {
            font-family: 'Courier New', Courier, monospace;
            background: #333; /* Dark gray for the time boxes */
            color: #fff;
            padding: 20px;
            border-radius: 19px;
            font-size: 18px;
            width: 55px;
            text-align: center;
        }

        .label {
            font-size:10px;
            color:rgb(255, 255, 255); /* Darker gray for labels */
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <!-- Countdown Section -->
    <div class="countdown-container">
      
        <div class="countdown">
            <div class="time-unit" id="days">
                30<span class="label">Days</span>
            </div>
            <div class="time-unit" id="hours">
                00<span class="label">Hours</span>
            </div>
            <div class="time-unit" id="minutes">
                00<span class="label">Minutes</span>
            </div>
            <div class="time-unit" id="seconds">
                00<span class="label">Seconds</span>
            </div>
        </div>
    </div>

    <script>
        // Set the date we're counting down to (30 days from now)
        var countDownDate = new Date(new Date().getTime() + 30 * 24 * 60 * 60 * 1000).getTime();

        // Update the count down every 1 second
        var countdownFunction = setInterval(function() {
            var now = new Date().getTime();
            var distance = countDownDate - now;

            // Time calculations for days, hours, minutes, and seconds
            var days = Math.floor(distance / (1000 * 60 * 60 * 24));
            var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            var seconds = Math.floor((distance % (1000 * 60)) / 1000);

            // Display the result in the elements
            document.getElementById("days").innerHTML = days + "<span class='label'>Days</span>";
            document.getElementById("hours").innerHTML = hours + "<span class='label'>Hours</span>";
            document.getElementById("minutes").innerHTML = minutes + "<span class='label'>Minutes</span>";
            document.getElementById("seconds").innerHTML = seconds + "<span class='label'>Seconds</span>";

            // If the countdown is finished
            if (distance < 0) {
                clearInterval(countdownFunction);
                document.querySelector(".countdown").innerHTML = "Event has started!";
            }
        }, 1000);
    </script>

</body>
</html>
