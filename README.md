# Group-8-Project--Airline-Reservation-System-
Sprint 1 (Weeks 1 and 2) – Sprint 2 (Weeks 3 and 4).

# airlinereservationsystemgroup8.net
ARRIVAL,DEPARTURE,DESTINATION,ID,PRICE,ADMINVIEW,AGENTSALESPER,STATUS,RESERVATION  in PYTHON 

**********<<<<<<   ** ARRIVAL coding**  >>>>>>   *************
import tkinter as tk
from tkinter import ttk, messagebox
from datetime import datetime

class AirlineArrivalSystem:
    def __init__(self, root):
        self.root = root
        self.root.title("ARRIVAL — Airline Reservation System")
        self.root.configure(bg='#1e3c72')
        
        # Set window size and center it
        window_width = 700
        window_height = 600
        screen_width = root.winfo_screenwidth()
        screen_height = root.winfo_screenheight()
        x = (screen_width - window_width) // 2
        y = (screen_height - window_height) // 2
        self.root.geometry(f"{window_width}x{window_height}+{x}+{y}")
        
        self.setup_ui()
    
    def setup_ui(self):
        # Header
        header_frame = tk.Frame(self.root, bg='rgba(0,0,0,0.4)', height=80)
        header_frame.pack(fill='x', pady=(0, 
----------------------------------------<<<< **DEPARTURE**   >>>>> -------------------------------------------------------------------

        # departure.py - Flask web application for departure information
from flask import Flask, render_template_string, request

app = Flask(__name__)

# HTML template with embedded CSS and JavaScript
HTML_TEMPLATE = '''
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DEPARTURE — Airline Reservation System</title>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #1e3c72, #2a5298);
        color: #fff;
        text-transform: uppercase;
    }

    header {
        background: rgba(0,0,0,0.4);
        padding: 20px;
        text-align: center;
        font-size: 2rem;
        letter-spacing: 3px;
    }

    .container {
        width: 90%;
        max-width: 600px;
        margin: 40px auto;
        background: rgba(255,255,255,0.1);
        padding: 25px;
        border-radius: 10px;
        backdrop-filter: blur(6px);
    }

    label {
        display: block;
        margin-top: 15px;
        font-size: 1rem;
    }

--------------------------------------<<<<<<< **DESTINATION** >>>>>>>-------------------------------------------
from flask import Flask, render_template_string, request

app = Flask(__name__)

# The HTML template (preserving all CSS, JS, and layout from the original)
HTML_TEMPLATE = """
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DESTINATION — Airline Reservation System</title>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #004e92, #000428);
        color: #fff;
        text-transform: uppercase;
    }

    header {
        background: rgba(0,0,0,0.5);
        padding: 20px;
        text-align: center;
        font-size: 2rem;
        letter-spacing: 3px;
    }

    .container {
        width: 90%;
        max-width: 600px;
        margin: 40px auto;
        background: rgba(255,255,255,0.1);
        padding: 25px;
        border-radius: 10px;
        backdrop-filter: blur(6px);
    }

    label {
        display: block;
        margin-top: 15px;
        font-size: 1rem;
    }

    input {
        width: 100%;
        padding: 10px;
        margin-top: 5px;
        border-radius: 5px;
        border: none;
        font-size: 1rem;
    }

    button {
        margin-top: 20px;
        width: 100%;
        padding: 12px;
        background: #ff9800;
        border: none;
        border-radius: 5px;
        font-size: 1.1rem;
        cursor: pointer;
    }

    button:hover {
        background: #ffb74d;
    }

    .result {
        margin-top: 25px;
        padding: 15px;
        background: rgba(0,0,0,0.3);
        border-radius: 5px;
        font-size: 1.1rem;
        text-align: center;
    }
</style>

<script>
// JavaScript validation (Maintained from original)
function validateDestination() {
    const city = document.getElementById("city").value.trim();
    const country = document.getElementById("country").value.trim();
    const airport = document.getElementById("airport").value.trim();

    if (!city || !country || !airport) {
        alert("All fields are required.");
        return false;
    }
    return true;
}
</script>

</head>
<body>

<header>Destination Information</header>

<div class="container">
    <form method="POST" onsubmit="return validateDestination()">
        <label for="city">City</label>
        <input type="text" id="city" name="city" placeholder="e.g., Paris" value="{{ city_val }}">

        <label for="country">Country</label>
        <input type="text" id="country" name="country" placeholder="e.g., France" value="{{ country_val }}">

        <label for="airport">Airport Code</label>
        <input type="text" id="airport" name="airport" placeholder="e.g., CDG" value="{{ airport_val }}">

        <button type="submit">Save Destination</button>
    </form>

    {% if destination_message %}
        <div class="result">
            {{ destination_message }}
        </div>
    {% endif %}
</div>

</body>
</html>
"""

@app.route('/', methods=['GET', 'POST'])
def destination():
    destination_message = ""
    city_val = ""
    country_val = ""
    airport_val = ""

    if request.method == "POST":
        # Retrieve form data
        city_val = request.form.get("city", "")
        country_val = request.form.get("country", "")
        airport_val = request.form.get("airport", "")

        # Logic for processing destination info
        if city_val and country_val and airport_val:
            destination_message = f"Destination set: {city_val}, {country_val} — Airport Code: {airport_val}."
        else:
            destination_message = "All fields must be completed before submitting."

    return render_template_string(
        HTML_TEMPLATE, 
        destination_message=destination_message,
        city_val=city_val,
        country_val=country_val,
        airport_val=airport_val
    )

if __name__ == '__main__':
    # Run the application
    app.run(debug=True)

---------------------------------------------<<<<<<< **ID** >>>>>>>------------------------------------------------------------
from flask import Flask, request, render_template_string, redirect, url_for

app = Flask(__name__)

# HTML template (keeps the original styling, JS validation, and layout)
TEMPLATE = """
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RESERVATION — Airline Reservation System</title>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
        color: #fff;
        text-transform: uppercase;
    }

    header {
        background: rgba(0,0,0,0.5);
        padding: 20px;
        text-align: center;
        font-size: 2rem;
        letter-spacing: 3px;
    }

    .container {
        width: 90%;
        max-width: 650px;
        margin: 40px auto;
        background: rgba(255,255,255,0.1);
        padding: 25px;
        border-radius: 10px;
        backdrop-filter: blur(6px);
    }

    label {
        display: block;
        margin-top: 15px;
        font-size: 1rem;
    }

    input, select {
        width: 100%;
        padding: 10px;
        margin-top: 5px;
        border-radius: 5px;
        border: none;
        font-size: 1rem;
    }

    button {
        margin-top: 20px;
        width: 100%;
        padding: 12px;
        background: #ff9800;
        border: none;
        border-radius: 5px;
        font-size: 1.1rem;
        cursor: pointer;
    }

    button:hover {
        background: #ffb74d;
    }

    .result {
        margin-top: 25px;
        padding: 15px;
        background: rgba(0,0,0,0.3);
        border-radius: 5px;
        font-size: 1.1rem;
        text-align: center;
    }
</style>

<script>
// JavaScript validation
function validateReservation() {
    const fields = ["name", "flight", "destination", "seat", "date"];
    for (let f of fields) {
        if (!document.getElementById(f).value.trim()) {
            alert("All fields are required.");
            return false;
        }
    }
    return true;
}
</script>

</head>
<body>

<header>Flight Reservation</header>

<div class="container">
    <form method="POST" onsubmit="return validateReservation()">

        <label>Passenger Name</label>
        <input type="text" id="name" name="name" placeholder="e.g., John Smith" value="{{ form_values.name }}">

        <label>Flight Number</label>
        <input type="text" id="flight" name="flight" placeholder="e.g., AA204" value="{{ form_values.flight }}">

        <label>Destination</label>
        <input type="text" id="destination" name="destination" placeholder="e.g., Miami" value="{{ form_values.destination }}">

        <label>Seat Number</label>
        <input type="text" id="seat" name="seat" placeholder="e.g., 12A" value="{{ form_values.seat }}">

        <label>Travel Date</label>
        <input type="date" id="date" name="date" value="{{ form_values.date }}">

        <button type="submit">Submit Reservation</button>
    </form>

    {% if reservation_message %}
        <div class="result">
            {{ reservation_message }}
        </div>
    {% endif %}
</div>

</body>
</html>
"""

def _trim_field(value):
    """Helper to safely trim form fields (like PHP's trim)."""
    if value is None:
        return ""
    return str(value).strip()

@app.route("/", methods=["GET", "POST"])
def reservation():
    """
    Handles GET and POST for the reservation page.
    - On GET: renders the form with empty fields.
    - On POST: validates inputs (server-side), sets a confirmation or error message,
      and re-renders the page showing the message.
    """
    reservation_message = ""
    # Default form values for re-population
    form_values = {
        "name": "",
        "flight": "",
        "destination": "",
        "seat": "",
        "date": ""
    }

    if request.method == "POST":
        # Trim and fetch fields, analogous to the original PHP logic
        name = _trim_field(request.form.get("name"))
        flight = _trim_field(request.form.get("flight"))
        destination = _trim_field(request.form.get("destination"))
        seat = _trim_field(request.form.get("seat"))
        date = _trim_field(request.form.get("date"))

        # Keep values to re-populate the form after submission
        form_values.update({
            "name": name,
            "flight": flight,
            "destination": destination,
            "seat": seat,
            "date": date
        })

        # Server-side validation: ensure all fields are present and non-empty
        if name and flight and destination and seat and date:
            # Match the PHP confirmation message format exactly
            reservation_message = (
                f"Reservation Confirmed for {name} — Flight {flight} to {destination} on {date} (Seat {seat})."
            )
        else:
            reservation_message = "All fields must be completed before submitting."

    return render_template_string(
        TEMPLATE,
        reservation_message=reservation_message,
        form_values=form_values
    )

if __name__ == "__main__":
    # Run the app in debug mode for development. In production, use a proper WSGI server.
    app.run(debug=True, host="127.0.0.1", port=5000)

-------------------------------------------------------<<<<<<< **PRICE** >>>>>>>------------------------------------------------------
from flask import Flask, request, render_template_string

app = Flask(__name__)

TEMPLATE = '''
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PRICE — Airline Reservation System</title>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #283c86, #45a247);
        color: #fff;
        text-transform: uppercase;
    }

    header {
        background: rgba(0,0,0,0.4);
        padding: 20px;
        text-align: center;
        font-size: 2rem;
        letter-spacing: 3px;
    }

    .container {
        width: 90%;
        max-width: 600px;
        margin: 40px auto;
        background: rgba(255,255,255,0.1);
        padding: 25px;
        border-radius: 10px;
        backdrop-filter: blur(6px);
    }

    label {
        display: block;
        margin-top: 15px;
        font-size: 1rem;
    }

    input {
        width: 100%;
        padding: 10px;
        margin-top: 5px;
        border-radius: 5px;
        border: none;
        font-size: 1rem;
    }

    button {
        margin-top: 20px;
        width: 100%;
        padding: 12px;
        background: #ffd700;
        border: none;
        border-radius: 5px;
        font-size: 1.1rem;
        cursor: pointer;
    }

    button:hover {
        background: #ffea4d;
    }

    .result {
        margin-top: 25px;
        padding: 15px;
        background: rgba(0,0,0,0.3);
        border-radius: 5px;
        font-size: 1.1rem;
        text-align: center;
    }
</style>

<script>
// JavaScript validation
function validatePrice() {
    const base = document.getElementById("base").value.trim();
    const tax = document.getElementById("tax").value.trim();
    const fees = document.getElementById("fees").value.trim();

    if (!base || !tax || !fees) {
        alert("Base price, tax, and fees are required.");
        return false;
    }

    if (isNaN(base) || isNaN(tax) || isNaN(fees)) {
        alert("Please enter valid numeric values.");
        return false;
    }

    return true;
}
</script>

</head>
<body>

<header>Ticket Price Calculator</header>

<div class="container">
    <form method="POST" onsubmit="return validatePrice()">
        <label>Base Ticket Price ($)</label>
        <input type="text" id="base" name="base" placeholder="e.g., 250">

        <label>Tax Amount ($)</label>
        <input type="text" id="tax" name="tax" placeholder="e.g., 35">

        <label>Additional Fees ($)</label>
        <input type="text" id="fees" name="fees" placeholder="e.g., 20">

        <label>Discount ($) — Optional</label>
        <input type="text" id="discount" name="discount" placeholder="e.g., 10">

        <button type="submit">Calculate Price</button>
    </form>

    {% if price_message %}
        <div class="result">
            {{ price_message }}
        </div>
    {% endif %}
</div>

</body>
</html>
'''

def safe_float(value):
    """Safely convert string to float, default to 0.0 like PHP floatval."""
    try:
        return float(value or 0)
    except (ValueError, TypeError):
        return 0.0

@app.route('/', methods=['GET', 'POST'])
def index():
    price_message = ""
    if request.method == 'POST':
        base = safe_float(request.form.get('base'))
        tax = safe_float(request.form.get('tax'))
        fees = safe_float(request.form.get('fees'))
        discount = safe_float(request.form.get('discount'))

        if base > 0 and tax >= 0 and fees >= 0:
            subtotal = base + tax + fees
            final = subtotal - discount
            if final < 0:
                final = 0
            price_message = f"Final Ticket Price: ${final:.2f}"
        else:
            price_message = "Please enter valid price values."
    
    return render_template_string(TEMPLATE, price_message=price_message)

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=5000)

---------------------------------------------------------<<<<<<< **ADMINVIEW** >>>>>>>---------------------------------------------------
from flask import Flask, request, render_template_string

app = Flask(__name__)

# adminview.py — backend logic for loading reservation data
# Example static data (replace with database queries later)
reservations = [
    {"flight": "AA204", "name": "John Smith", "destination": "Miami", "price": 320},
    {"flight": "DL118", "name": "Sarah Johnson", "destination": "Chicago", "price": 280},
    {"flight": "UA990", "name": "Carlos Rivera", "destination": "Los Angeles", "price": 450},
    {"flight": "SW550", "name": "Emily Davis", "destination": "Houston", "price": 210},
]

@app.route('/', methods=['GET', 'POST'])
def adminview():
    search = request.form.get("search", "") if request.method == 'POST' else ""
    filtered = reservations[:]

    if search:
        search_lower = search.lower()
        filtered = [
            r for r in reservations
            if (search_lower in r["flight"].lower() or
                search_lower in r["name"].lower() or
                search_lower in r["destination"].lower())
        ]

    total = len(reservations)

    html_template = '''
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ADMINVIEW — Airline Reservation System</title>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #232526, #414345);
        color: #fff;
        text-transform: uppercase;
    }

    header {
        background: rgba(0,0,0,0.5);
        padding: 20px;
        text-align: center;
        font-size: 2rem;
        letter-spacing: 3px;
    }

    .container {
        width: 95%;
        max-width: 900px;
        margin: 40px auto;
        background: rgba(255,255,255,0.1);
        padding: 25px;
        border-radius: 10px;
        backdrop-filter: blur(6px);
    }

    .stats {
        display: flex;
        justify-content: space-between;
        margin-bottom: 25px;
    }

    .stat-box {
        width: 30%;
        background: rgba(0,0,0,0.3);
        padding: 15px;
        border-radius: 8px;
        text-align: center;
        font-size: 1.2rem;
    }

    table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 15px;
    }

    th, td {
        padding: 12px;
        border-bottom: 1px solid rgba(255,255,255,0.3);
        text-align: left;
    }

    th {
        background: rgba(0,0,0,0.4);
    }

    input {
        width: 100%;
        padding: 10px;
        border-radius: 5px;
        border: none;
        margin-top: 10px;
        font-size: 1rem;
    }

    button {
        margin-top: 15px;
        width: 100%;
        padding: 12px;
        background: #ff9800;
        border: none;
        border-radius: 5px;
        font-size: 1.1rem;
        cursor: pointer;
    }

    button:hover {
        background: #ffb74d;
    }
</style>

<script>
// Optional: Live search without submitting
function liveFilter() {
    const input = document.getElementById("search").value.toLowerCase();
    const rows = document.querySelectorAll("tbody tr");

    rows.forEach(row => {
        const text = row.innerText.toLowerCase();
        row.style.display = text.includes(input) ? "" : "none";
    });
}
</script>

</head>
<body>

<header>Administrator Dashboard</header>

<div class="container">

    <!-- System Stats -->
    <div class="stats">
        <div class="stat-box">Total Reservations: {{ total }}</div>
        <div class="stat-box">Destinations: 4</div>
        <div class="stat-box">System Status: Active</div>
    </div>

    <!-- Search Form -->
    <form method="POST">
        <input type="text" id="search" name="search" placeholder="Search by flight, name, or destination" onkeyup="liveFilter()">
        <button type="submit">Search</button>
    </form>

    <!-- Results Table -->
    <table>
        <thead>
            <tr>
                <th>Flight</th>
                <th>Passenger</th>
                <th>Destination</th>
                <th>Price ($)</th>
            </tr>
        </thead>
        <tbody>
            {% for r in filtered %}
                <tr>
                    <td>{{ r.flight }}</td>
                    <td>{{ r.name }}</td>
                    <td>{{ r.destination }}</td>
                    <td>{{ r.price }}</td>
                </tr>
            {% endfor %}
        </tbody>
    </table>

</div>

</body>
</html>
    '''
    return render_template_string(html_template, filtered=filtered, total=total)

if __name__ == '__main__':
    app.run(debug=True, host='127.0.0.1', port=5000)

-----------------------------------------------------<<<<<<< **AGENTSALESPER** >>>>>>>----------------------------------------------
# agentsalesper.py — backend logic for agent sales performance
# This is a Flask web application that replicates the PHP functionality

from flask import Flask, render_template_string, request
import math

app = Flask(__name__)

# Example static data (replace with database queries later)
agents = [
    {"name": "Agent Williams", "sales": 25, "total": 100},
    {"name": "Agent Martinez", "sales": 40, "total": 100},
    {"name": "Agent Chen", "sales": 15, "total": 100},
    {"name": "Agent Patel", "sales": 20, "total": 100},
]

def filter_agents(search_term):
    """Filter agents based on search term"""
    if not search_term:
        return agents
    
    filtered = []
    search_lower = search_term.lower()
    for agent in agents:
        if search_lower in agent["name"].lower():
            filtered.append(agent)
    return filtered

def calculate_performance(sales, total):
    """Calculate performance percentage"""
    if total == 0:
        return 0.0
    return (sales / total) * 100

def get_top_performer():
    """Get the top performing agent"""
    if not agents:
        return "None"
    
    top_agent = max(agents, key=lambda x: x["sales"])
    return top_agent["name"]

@app.route('/', methods=['GET', 'POST'])
def agent_sales_performance():
    # Handle search filter
    search = request.form.get("search", "")
    filtered_agents = filter_agents(search)
    
    # Calculate statistics
    total_agents = len(agents)
    top_performer = get_top_performer()
    
    # Calculate performance for each agent
    for agent in filtered_agents:
        agent["performance"] = calculate_performance(agent["sales"], agent["total"])
    
    # HTML template
    html_template = '''
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AGENT SALES PERFORMANCE — Airline Reservation System</title>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
        color: #fff;
        text-transform: uppercase;
    }

    header {
        background: rgba(0,0,0,0.5);
        padding: 20px;
        text-align: center;
        font-size: 2rem;
        letter-spacing: 3px;
    }

    .container {
        width: 95%;
        max-width: 900px;
        margin: 40px auto;
        background: rgba(255,255,255,0.1);
        padding: 25px;
        border-radius: 10px;
        backdrop-filter: blur(6px);
    }

    .stats {
        display: flex;
        justify-content: space-between;
        margin-bottom: 25px;
    }

    .stat-box {
        width: 30%;
        background: rgba(0,0,0,0.3);
        padding: 15px;
        border-radius: 8px;
        text-align: center;
        font-size: 1.2rem;
    }

    table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 15px;
    }

    th, td {
        padding: 12px;
        border-bottom: 1px solid rgba(255,255,255,0.3);
        text-align: left;
    }

    th {
        background: rgba(0,0,0,0.4);
    }

    input {
        width: 100%;
        padding: 10px;
        border-radius: 5px;
        border: none;
        margin-top: 10px;
        font-size: 1rem;
    }

    button {
        margin-top: 15px;
        width: 100%;
        padding: 12px;
        background: #ff9800;
        border: none;
        border-radius: 5px;
        font-size: 1.1rem;
        cursor: pointer;
    }

    button:hover {
        background: #ffb74d;
    }
</style>

<script>
// Optional: Live search without submitting
function liveFilter() {
    const input = document.getElementById("search").value.toLowerCase();
    const rows = document.querySelectorAll("tbody tr");

    rows.forEach(row => {
        const text = row.innerText.toLowerCase();
        row.style.display = text.includes(input) ? "" : "none";
    });
}
</script>

</head>
<body>

<header>Agent Sales Performance</header>

<div class="container">

    <!-- System Stats -->
    <div class="stats">
        <div class="stat-box">Total Agents: {{ total_agents }}</div>
        <div class="stat-box">Top Performer: {{ top_performer }}</div>
        <div class="stat-box">System Status: Active</div>
    </div>

    <!-- Search Form -->
    <form method="POST">
        <input type="text" id="search" name="search" placeholder="Search agent name" 
               value="{{ search_term }}" onkeyup="liveFilter()">
        <button type="submit">Search</button>
    </form>

    <!-- Results Table -->
    <table>
        <thead>
            <tr>
                <th>Agent Name</th>
                <th>Tickets Sold</th>
                <th>Total Possible</th>
                <th>Performance (%)</th>
            </tr>
        </thead>
        <tbody>
            {% for agent in filtered_agents %}
                <tr>
                    <td>{{ agent.name }}</td>
                    <td>{{ agent.sales }}</td>
                    <td>{{ agent.total }}</td>
                    <td>
                        {{ "%.2f"|format(agent.performance) }}%
                    </td>
                </tr>
            {% endfor %}
        </tbody>
    </table>

</div>

</body>
</html>
'''
    
    return render_template_string(
        html_template,
        filtered_agents=filtered_agents,
        total_agents=total_agents,
        top_performer=top_performer,
        search_term=search
    )

if __name__ == '__main__':
    app.run(debug=True)

--------------------------------------------------------<<<<<<< **STATUS** >>>>>>>---------------------------------------------------
# app.py
from flask import Flask, render_template, request, escape

app = Flask(__name__)
app.config['TEMPLATES_AUTO_RELOAD'] = True  # autoreload templates during development

# Example static data (replace with database queries later)
flights = [
    {"flight": "AA204", "destination": "Miami", "status": "On Time"},
    {"flight": "DL118", "destination": "Chicago", "status": "Delayed"},
    {"flight": "UA990", "destination": "Los Angeles", "status": "Boarding"},
    {"flight": "SW550", "destination": "Houston", "status": "Cancelled"},
]


@app.route("/", methods=["GET", "POST"])
def status_lookup():
    """
    Handle the flight status lookup form:
    - GET: render the empty form
    - POST: normalize input, search in `flights`, and render result
    """
    search_result = None
    found = False

    if request.method == "POST":
        # Get and sanitize user input
        flight_number = request.form.get("flightNumber", "")
        # Equivalent of strtoupper(trim(...))
        flight_number = flight_number.strip().upper()

        # Search for the flight
        for f in flights:
            if f.get("flight", "").upper() == flight_number:
                # Use a shallow copy to avoid accidental mutation
                search_result = dict(f)
                found = True
                break

        if not found:
            search_result = "Flight not found."

    # Render the template, passing the search result and found flag
    return render_template("status.html", search_result=search_result, found=found)


if __name__ == "__main__":
    # Run the Flask development server
    app.run(debug=True, host="127.0.0.1", port=5000)

-------------------------------------------------------<<<<<<< **RESERVATION** >>>>>>>----------------------------------------------------
<?php
// reservation.php — backend logic for creating a reservation

$reservationMessage = "";

if ($_SERVER["REQUEST_METHOD"] === "POST") {
    $name = trim($_POST["name"] ?? "");
    $flight = trim($_POST["flight"] ?? "");
    $destination = trim($_POST["destination"] ?? "");
    $seat = trim($_POST["seat"] ?? "");
    $date = trim($_POST["date"] ?? "");

    if ($name && $flight && $destination && $seat && $date) {
        $reservationMessage = 
            "Reservation Confirmed for $name — Flight $flight to $destination on $date (Seat $seat).";
    } else {
        $reservationMessage = "All fields must be completed before submitting.";
    }
}
?>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RESERVATION — Airline Reservation System</title>

<style>
    body {
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
        color: #fff;
        text-transform: uppercase;
    }

    header {
        background: rgba(0,0,0,0.5);
        padding: 20px;
        text-align: center;
        font-size: 2rem;
        letter-spacing: 3px;
    }

    .container {
        width: 90%;
        max-width: 650px;
        margin: 40px auto;
        background: rgba(255,255,255,0.1);
        padding: 25px;
        border-radius: 10px;
        backdrop-filter: blur(6px);
    }

    label {
        display: block;
        margin-top: 15px;
        font-size: 1rem;
    }

    input, select {
        width: 100%;
        padding: 10px;
        margin-top: 5px;
        border-radius: 5px;
        border: none;
        font-size: 1rem;
    }

    button {
        margin-top: 20px;
        width: 100%;
        padding: 12px;
        background: #ff9800;
        border: none;
        border-radius: 5px;
        font-size: 1.1rem;
        cursor: pointer;
    }

    button:hover {
        background: #ffb74d;
    }

    .result {
        margin-top: 25px;
        padding: 15px;
        background: rgba(0,0,0,0.3);
        border-radius: 5px;
        font-size: 1.1rem;
        text-align: center;
    }
</style>

<script>
// JavaScript validation
function validateReservation() {
    const fields = ["name", "flight", "destination", "seat", "date"];
    for (let f of fields) {
        if (!document.getElementById(f).value.trim()) {
            alert("All fields are required.");
            return false;
        }
    }
    return true;
}
</script>

</head>
<body>

<header>Flight Reservation</header>

<div class="container">
    <form method="POST" onsubmit="return validateReservation()">

        <label>Passenger Name</label>
        <input type="text" id="name" name="name" placeholder="e.g., John Smith">

        <label>Flight Number</label>
        <input type="text" id="flight" name="flight" placeholder="e.g., AA204">

        <label>Destination</label>
        <input type="text" id="destination" name="destination" placeholder="e.g., Miami">

        <label>Seat Number</label>
        <input type="text" id="seat" name="seat" placeholder="e.g., 12A">

        <label>Travel Date</label>
        <input type="date" id="date" name="date">

        <button type="submit">Submit Reservation</button>
    </form>

    <?php if ($reservationMessage): ?>
        <div class="result">
            <?php echo $reservationMessage; ?>
        </div>
    <?php endif; ?>
</div>

</body>
</html>

-----------------------------------------------------------------------------------------------------------------------------------------------
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

