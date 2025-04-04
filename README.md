# MIRROR-MOMENTS
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skincare Routine Tracker</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: linear-gradient(to bottom, #ffd7be, #ffe6cc);
        }
        .calendar {
            width: 80%;
            margin: 40px auto;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .calendar-header {
            background-color: #f0f0f0;
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
        .calendar-header th {
            font-weight: bold;
        }
        .calendar-body {
            padding: 10px;
        }
        .day {
            width: 14.28%;
            height: 100px;
            border: 1px solid #ddd;
            display: inline-block;
            margin: 10px;
            padding: 10px;
            background-color: #f0f0f0;
            border-radius: 10px;
        }
        .day:hover {
            background-color: #e0e0e0;
        }
        .active-day {
            background-color: #ccc;
        }
        .logged-activities {
            margin-top: 40px;
        }
        .activity {
            margin-bottom: 10px;
            padding: 10px;
            border: 1px solid #ddd;
            background-color: #f0f0f0;
            border-radius: 10px;
        }
        .activity:hover {
            background-color: #e0e0e0;
        }
        .completed {
            background-color: #c6efce;
        }
        .flower {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 50px;
            color: #ff69b4;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="text-center">Skincare Routine Tracker <i class="fa fa-flower"></i></h1>
        <div class="self-care-goals">
            <h2>Set Your Weekly Self-Care Goals</h2>
            <form>
                <div class="mb-3">
                    <label for="moisturizing-goal" class="col-form-label">Moisturizing Goal:</label>
                    <input type="number" class="form-control" id="moisturizing-goal" value="3">
                </div>
                <div class="mb-3">
                    <label for="facials-goal" class="col-form-label">Facials Goal:</label>
                    <input type="number" class="form-control" id="facials-goal" value="2">
                </div>
                <button type="button" class="btn btn-primary" id="set-goals-btn">Set Goals</button>
            </form>
            <div class="progress-bar">
                <div class="progress" style="width: 0%;"></div>
            </div>
            <p id="progress-text"></p>
        </div>
        <div class="mood-selector">
            <h2>How Are You Feeling Today?</h2>
            <select class="form-select" id="mood-selector">
                <option value="tired">😴</option>
                <option value="stressed">😬</option>
                <option value="happy">😊</option>
            </select>
            <p id="mood-tip"></p>
            <textarea class="form-control" id="personal-note" placeholder="Write a note to yourself"></textarea>
            <button type="button" class="btn btn-primary" id="save-note-btn">Save Note</button>
            <p id="daily-note"></p>
        </div>
        <div class="routine-reminders">
            <h2>Enable Routine Reminders</h2>
            <button type="button" class="btn btn-primary" id="enable-reminders-btn">Enable Reminders</button>
        </div>
        <div class="calendar">
            <div class="calendar-header">
                <table style="width: 100%;">
                    <tr>
                        <th>Sun</th>
                        <th>Mon</th>
                        <th>Tue</th>
                        <th>Wed</th>
                        <th>Thu</th>
                        <th>Fri</th>
                        <th>Sat</th>
                    </tr>
                </table>
            </div>
            <div class="calendar-body">
                <div class="row row-cols-7 g-3">
                    <div class="col day" id="day-1">1 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-2">2 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-3">3 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-4">4 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-5">5 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-6">6 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-7">7 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-8">8 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-9">9 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-10">10 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-11">11 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-12">12 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-13">13 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-14">14 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-15">15 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-16">16 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-17">17 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-18">18 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-19">19 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-20">20 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-21">21 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-22">22 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-23">23 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-24">24 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-25">25 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-26">26 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-27">27 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-28">28 <i class="fa fa-flower"></i></div>
                    <div class="col day" id="day-29">29 <i class="fa fa-leaf"></i></div>
                    <div class="col day" id="day-30">30 <i class="fa fa-seedling"></i></div>
                    <div class="col day" id="day-31">31 <i class="fa fa-flower"></i></div>
                </div>
            </div>
        </div>
        <div class="logged-activities">
            <h2>Logged Activities</h2>
            <div id="activities-list"></div>
        </div>
        <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#log-activity-modal">
            Log Activity
        </button>
        <div class="modal fade" id="log-activity-modal" tabindex="-1" aria-labelledby="log-activity-modal-label" aria-hidden="true">
            <div class="modal-dialog">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title" id="log-activity-modal-label">Log Activity</h5>
                        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                    </div>
                    <div class="modal-body">
                        <form>
                            <div class="mb-3">
                                <label for="activity-type" class="col-form-label">Activity Type:</label>
                                <select class="form-select" id="activity-type">
                                    <option value="cleansing">Cleansing</option>
                                    <option value="toning">Toning</option>
                                    <option value="moisturizing">Moisturizing</option>
                                    <option value="exfoliating">Exfoliating</option>
                                </select>
                            </div>
                            <div class="mb-3">
                                <label for="product-used" class="col-form-label">Product Used:</label>
                                <input type="text" class="form-control" id="product-used">
                            </div>
                            <div class="mb-3">
                                <label for="notes" class="col-form-label">Notes:</label>
                                <textarea class="form-control" id="notes"></textarea>
                            </div>
                            <div class="mb-3">
                                <label for="photo" class="col-form-label">Upload Photo:</label>
                                <input type="file" class="form-control" id="photo">
                            </div>
                        </form>
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                        <button type="button" class="btn btn-primary" id="log-activity-btn">Log Activity</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        let activities = {};
        let goals = {
            moisturizing: 0,
            facials: 0
        };
        let notes = [];
        let moodSuggestions = {
            "tired": ["Try a refreshing toner + massage today", "Get some rest and prioritize self-care"],
            "stressed": ["Try a calming face mask today", "Practice deep breathing exercises"],
            "happy": ["Keep up the good work! You're doing great", "Treat yourself to a relaxing bath"]
        };
        document.addEventListener("DOMContentLoaded", function() {
            const days = document.querySelectorAll(".day");
            days.forEach(day => {
                day.addEventListener("click", function() {
                    const dayId = day.id;
                    const activitiesList = document.getElementById("activities-list");
                    activitiesList.innerHTML = "";
                    if (activities[dayId]) {
                        activities[dayId].forEach(activity => {
                            const activityDiv = document.createElement("div");
                            activityDiv.classList.add("activity");
                            activityDiv.innerHTML = `
                                <h5>${activity.type}</h5>
                                <p>Product Used: ${activity.product}</p>
                                <p>Notes: ${activity.notes}</p>
                            `;
                            activitiesList.appendChild(activityDiv);
                        });
                    }
                    day.classList.add("active-day");
                });
            });
            document.getElementById("set-goals-btn").addEventListener("click", function() {
                goals.moisturizing = parseInt(document.getElementById("moisturizing-goal").value);
                goals.facias = parseInt(document.getElementById("facials-goal").value);
                const progressBar = document.querySelector(".progress-bar .progress");
                progressBar.style.width = "0%";
                document.getElementById("progress-text").innerHTML = `You have completed 0% of your goals`;
            });
            document.getElementById("mood-selector").addEventListener("change", function() {
                const mood = document.getElementById("mood-selector").value;
                const moodTip = document.getElementById("mood-tip");
                const note = document.getElementById("personal-note");
                const suggestions = moodSuggestions[mood];
                note.placeholder = suggestions[Math.floor(Math.random() * suggestions.length)];
                moodTip.innerHTML = suggestions[Math.floor(Math.random() * suggestions.length)];
            });
            document.getElementById("save-note-btn").addEventListener("click", function() {
                const note = document.getElementById("personal-note").value;
                notes.push(note);
                document.getElementById("daily-note").innerHTML = notes[Math.floor(Math.random() * notes.length)];
            });
            document.getElementById("log-activity-btn").addEventListener("click", function() {
                const dayId = document.querySelector(".active-day").id;
                const activityType = document.getElementById("activity-type").value;
                const productUsed = document.getElementById("product-used").value;
                const notes = document.getElementById("notes").value;
                const photo = document.getElementById("photo").files[0];
                if (!activities[dayId]) {
                    activities[dayId] = [];
                }
                activities[dayId].push({
                    type: activityType,
                    product: productUsed,
                    notes: notes,
                    photo: photo
                });
                document.getElementById("log-activity-modal").classList.remove("show");
                document.querySelector(".modal-backdrop").remove();
                const activitiesList = document.getElementById("activities-list");
                activitiesList.innerHTML = "";
                activities[dayId].forEach(activity => {
                    const activityDiv = document.createElement("div");
                    activityDiv.classList.add("activity");
                    activityDiv.innerHTML = `
                        <h5>${activity.type}</h5>
                        <p>Product Used: ${activity.product}</p>
                        <p>Notes: ${activity.notes}</p>
                        <img src="${URL.createObjectURL(activity.photo)}" alt="Photo">
                    `;
                    activitiesList.appendChild(activityDiv);
                });
                // Update progress bar
                const progressBar = document.querySelector(".progress-bar .progress");
                const progressText = document.getElementById("progress-text");
                let progress = 0;
                Object.keys(activities).forEach(day => {
                    activities[day].forEach(activity => {
                        if (activity.type === "moisturizing") {
                            progress++;
                        }
                    });
                });
                const goalProgress = (progress / goals.moisturizing) * 100;
                progressBar.style.width = `${goalProgress}%`;
                progressText.innerHTML = `You have completed ${goalProgress}% of your goals`;
            });
        });
    </script>
</body>
</html>
✨ Mirror Moments – Your Daily Self-Care Companion Mirror Moments is a gentle, personal self-care tracker designed especially for housewives. It encourages women to pause, reflect, and care for themselves beyond daily chores. With simple tools for skincare logging and emotional wellness, it celebrates small but powerful acts of self-love.
