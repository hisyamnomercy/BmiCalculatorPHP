## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/hisyamnomercy/BmiCalculatorPHP/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

<html>

<head>
	<meta charset="utf-8">
	<title>Form</title>
	<style>
	body {
		padding: 20px 20%;
	}
	
	form {
		padding: 10px 20px;
		background-color: #f5f5f5;
		border: solid thin #EEE;
		font-style: Helvetica;
		font-size: 12pt;
	}
	
	.result {
		padding: 10px 20px;
		background-color: #86877a;
		color: #FFF;
		border: solid thin #600;
	}
	</style>
</head>

<body>
	<h1>Get input & display input (Form)</h1>
	<h2>BMI calculator</h2>
	<form methot="get" action=""> Enter your name
		<br>
		<input type="text" name="name" style="background-color: #ffd9e3"  >
		<br> Select your gender 
		<br>
		<select name="sex" style="background-color: #bcd2f7">
			<option value=" "> </option>
			<option value="male">Male</option>
			<option value="female">Female</option>
		</select>
		<br> Height (cm)
		<br>
		<input type="text" name="h" style="background-color: #bcf7da" >
		<br> Weight (kg)
		<br>
		<input type="text" name="w" style="background-color: #f1f7bc">
		<br>
		<input type="submit" name="submit" value="Calculate BMI" style="background-color: #f7d1bc">
		<input type="reset" value="clear" name="reset" style="background-color: #bcf7e2" /> </form>
	<?php
if (isset($_GET['submit']))
{
    $name = $_GET['name'];
    $sex = $_GET['sex'];
    $h = $_GET['h'] / 100;
    $w = $_GET['w'];

    $bmi = $w / ($h * $h);

    echo '<div class="result">';
    echo "<h3>Your BMI result :</h3>";
    echo "Name: $name<br>";
    echo "Gender: $sex<br>";
    echo "Height : $h meter<br>";
    echo "Weight: $w kilogram<br>";
    echo "<hr>your BMI : $bmi";
    echo "<hr>Round off your BMI : " . number_format($bmi);
    echo "<h4>conclusion:</h4>";

    if ($bmi < 15.5)
    {
        echo "N/A";
    }
    elseif ($bmi < 18.5)
    {
        echo "Underweight";
    }
    elseif ($bmi < 25)
    {
        echo "Normal weight";
    }
    elseif ($bmi < 30)
    {
        echo "Overweight";
    }
    elseif ($bmi < 40)
    {
        echo "Obese";
    }
    else
    {
        echo "N/A";
    }

    echo '</div>';
}
?>
</body>

</html>
