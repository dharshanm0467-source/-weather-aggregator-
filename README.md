async function getWeather() {
    const city = document.getElementById("city").value;
    const apiKey = "YOUR_API_KEY";

    const response = await fetch(
        `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`
    );

    const data = await response.json();

    document.getElementById("weather").innerHTML =
        `<h2>${data.name}</h2>
         <p>Temperature: ${data.main.temp} °C</p>
         <p>Humidity: ${data.main.humidity}%</p>
         <p>Wind Speed: ${data.wind.speed} m/s</p>`;
}
