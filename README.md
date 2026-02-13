<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Don't Be Such A Chore... I mean, respect yourself a little.</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Arial, sans-serif;
            background: rgba(255,255,255,255);

        }

        .nothead {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2px;
            position: fixed;
           top: 0;
           right:0;
           left:0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
                font-size: 16px;
            text-shadow: 0 0 4px red;
      font-weight: bold;
      font-style: italic;
      justify-content: right;
      
}

        .header h1 {
            font-size: 14px;
            
        }

        .search-filter {
            margin-top: 1px;
        }
    
        .search-input {
            padding: 1px 2px;
                     border: 1px solid rgba(118,75,162,1);
            border-radius: 5px;
            font-size: 12px;
            position: relative;
            left: -1px;
            top: 0px;
            width: 30px;
            background: white;
            z-index: 200;
            cursor: text;

             box-shadow: 0 0 2px 1px red;
        }
        .search-input:focus {
            width: 70px;
        }
        .filter-btn {
            padding: 2px 5px 2px 5px;
            background: grey;
            border-radius: 5px;
            font-size: 10px;
            cursor: pointer;

            position: fixed;
            top: 2px;
            left: 245px;
        }
        .filter-btn2 {
padding: 2px 5px 2px 5px;
            background: grey;
            border-radius: 5px;
            font-size: 10px;
            cursor: pointer;

            position: fixed;
            top: 2px;
            left: 275px;
}
        .fltspn {
               margin-left: 2px;
               font-size: 12;
               }

        .filter-btn.active {
            background: rgba(118,75,162,1);
            border-color: red;
            color: white;
            font-weight: bold;
            cursor: not-allowed;
        }
        .filter-btn2.active {

background: rgba(118,75,162,1);
            border-color: red;
            color: white;
            font-weight: bold;
            cursor: not-allowed;
}

        .stats {
            display: flex;
            justify-content: space-around;
            padding: 15px 20px;
            background: white;
            margin-bottom: 10px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }

        .stat {
            text-align: center;
        }

        .stat-value {
            font-size: 24px;
            font-weight: bold;
            color: #667eea;
        }

        .stat-label {
            font-size: 12px;
            color: #666;
            margin-top: 4px;
        }

        .chore-list {
            padding: 15px;
        }

        /* Floor Section Styles */
        .floor-section {
            margin-bottom: 5px;
        }

        .floor-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 5px 20px;
            border-radius: 12px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 8px rgba(0,0,0,0.15);
            margin-bottom: 2px;
            user-select: none;
        }

        .floor-header.new-events {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .floor-header:active {
            transform: scale(0.98);
        }

        .floor-title {
            font-size: 18px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 45px;
        }

        .floor-badge {
            background: rgba(255,255,255,0.3);
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: 500;
        }

        .floor-chevron {
            font-size: 20px;
            transition: transform 0.3s ease;
        }

        .floor-chevron.collapsed {
            transform: rotate(-90deg);
        }

        .floor-content {
            max-height: 10000px;
            overflow: hidden;
            transition: max-height 0.3s ease;
        }

        .floor-content.collapsed {
            max-height: 0;
        }

        /* Room Section Styles */
        .room-section {
            margin-bottom: 5px;
            margin-left: 10px;
        }

        .room-header {
            background: white;
            padding: 5px 16px;
            border-radius: 10px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 6px rgba(0,0,0,0.48);
            margin-bottom: 4px;
            user-select: none;
        }

        .room-header:active {
            transform: scale(0.98);
            background: rgba(168,75,162,1);
        }

        .room-title {
            font-size: 16px;
            font-weight: 600;
            color: #333;
            display: flex;
            align-items: center;
            gap: 24px;
        }

        .room-badge {
            background: #e3f2fd;
            color: #1976d2;
            padding: 2px 8px;
            border-radius: 10px;
            font-size: 12px;
            font-weight: 500;
        }

        .room-chevron {
            font-size: 16px;
            transition: transform 0.3s ease;
            color: #666;
        }

        .room-chevron.collapsed {
            transform: rotate(-90deg);
        }

        .room-content {
            max-height: 10000px;
            overflow: hidden;
            transition: max-height 0.3s ease;
        }

        .room-content.collapsed {
            max-height: 0;
        }

        .chore-card {
            background: white;
            border-radius: 12px;
            padding: 5px;
            margin-bottom: 5px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            border-left: 4px solid green;
        }

        .chore-card.overdue {
            border-left-color: red;
        }

        .chore-card.due-soon {
            border-left-color: orange;
        }

        .chore-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 2px;

        }

        .chore-title {
            font-size: 16px;
            font-weight: 600;
            color: #333;
            line-height: 1.4;

        }

        .frequency-badge {
            background: #e3f2fd;
            color: #1976d2;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: 500;
            white-space: nowrap;
            margin-left: 8px;
        }

        .chore-info {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2px;
            margin-bottom: 1px;
        }

        .info-item {
            display: inline;
            flex-direction: column;
            gap: 4px;
        }

        .info-label {
            font-size: 11px;
            color: #999;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            gap: 2px 4px;
        }
        .info-label2 {
            font-size: 11px;
            color: white;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            border: 1px dashed black;
            background: grey;
        }

        .info-value {
            font-size: 14px;
            color: #333;
            font-weight: 500;
        }

        .status-badge {
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: 600;
            display: inline-block;
        }

        .status-good {
            background: #e8f5e9;
            color: #2e7d32;
        }

        .status-due-soon {
            background: #fff3e0;
            color: #ef6c00;
        }

        .status-overdue {
            background: #ffebee;
            color: #c62828;
        }

        .complete-btn {
            width: 100px;
            padding: 2px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.1s, opacity 0.2s;
        }

        .complete-btn:active {
            transform: scale(0.98);
        }

        .complete-btn.completed {
            background: #4caf50;
            opacity: 0.8;
        }

        .empty-state {
            text-align: center;
            padding: 60px 20px;
            color: #999;
        }

        .empty-state-icon {
            font-size: 64px;
            margin-bottom: 16px;
        }



        .bottom-nav {

            position: fixed;
            left: 6px;
            width: 349px;
            top: 22px;
            background: lightgrey;
            opacity: 70%;
            padding: 1px 0px 3px 0px;
            box-shadow: 0 -2px 12px rgba(118,75,162,1);
            align-items: right;
            z-index:600;
        }


        .nav-btn {
            padding: 2px 0 0 10px;
            background: none;
            border: none;
            color: black;
            font-size: 12px;
            cursor: pointer;
            font-weight: bold;
            gap: 1px;
            text-shadow: 1px 1px 6px 6px rgba(118,75,162,1);
            top: 50%;
        }
   .nav-btn2 {

            background: none;
            border: none;
            color: rgba(118,75,162,1);
            font-size: 12px;
            cursor: pointer;
            text-shadow: -1.5px -1.5px 5px red;
             top: 50%;

        }
        .nav-btn-icon {
            font-size: 12px;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            border-radius: 16px;
            padding: 24px;
            max-width: 500px;
            width: 90%;
            max-height: 180vh;
            overflow-y: auto;
        }

        .modal-header {
            font-size: 20px;
            font-weight: 600;
            margin-bottom: 20px;
            color: #333;
        }

        .form-group {
            margin-bottom: 16px;
        }

        .form-label {
            display: block;
            font-size: 14px;
            font-weight: 500;
            color: #333;
            margin-bottom: 6px;
        }

        .form-input, .form-select {
            width: 100%;
            padding: 10px 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 15px;
            font-family: inherit;
        }

        .form-input:focus, .form-select:focus {
            outline: none;
            border-color: #667eea;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
        }

        .checkbox-group {
            display: flex;
            gap: 16px;
            margin-top: 8px;
        }

        .checkbox-label {
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 14px;
            cursor: pointer;
        }

        .checkbox-label input {
            cursor: pointer;
        }

        .day-mask-group {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 8px;
            margin-top: 8px;
        }

        .day-checkbox {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
        }

        .day-checkbox input {
            cursor: pointer;
        }

        .day-checkbox label {
            font-size: 11px;
            color: #666;
            cursor: pointer;
        }

        .button-group {
            display: flex;
            gap: 12px;
            margin-top: 24px;
        }

        .btn-primary {
            flex: 1;
            padding: 12px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
        }

        .btn-secondary {
            flex: 1;
            padding: 12px;
            background: #f5f5f5;
            color: #333;
            border: none;
            border-radius: 8px;
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
        }

        .add-event-section {
            margin-left: 10px;
        }

        .add-event-btn {
            background: white;
            padding: 20px;
            border-radius: 12px;
            border: 2px dashed #667eea;
            color: #667eea;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }

        .add-event-btn:active {
            transform: scale(0.98);
        }

        .delete-btn {
            width: 100%;
            padding: 10px;
            background: #f44336;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            margin-top: 8px;
        }

        .delete-btn:active {
            transform: scale(0.98);
        }
        .navtext {
            font-size: 10;
            top: 50%
            color:black
            }

        #fileInput {
            display: none;
        }
        #searchInput {
             padding-right: 15px;
        }
         #clearButton {
            position: relative;
            right: 17px;
            top: 50%;

            border: 1px solid grey;
            background: grey;
            cursor: pointer;
            z-index: 500;
            border-radius: 8px;
            font-size: 10px;
            color: white;
        }
    </style>
</head>
<body>   
   <div class ="nothead">
     
        <button class="nav-btn2" id="exportData">💾 </button>You Are A Filthy Chore
        <button class="nav-btn2" id="importData"> 📂 </button>
<span class="search-filter">
        <input type="text" id="searchInput" class="search-input" placeholder=" Search " >
        <button id="clearButton">X</button>
            <button id="filterAll" class="filter-btn active">All</button><button id="filterOverdue" class="filter-btn2">DUE</button>
</span>

 </div>
 <div class="bottom-nav">
    <button class="nav-btn" id="expandAll">⬇️  Expand ALL
 ⬇️       </button>
        <button class="nav-btn" id="collapseAll">
            ⬆️  Collapse ALL  ⬆️
        </button> <button class ="nav-btn" onclick="scrollToTop()">^Back to Top^</button>  </div>  
    
    <div class="stats">
        <div class="stat">
            <div class="stat-value" id="overdueCount">0</div>
            <div class="stat-label">Overdue</div>
        </div>
        <div class="stat">
            <div class="stat-value" id="dueSoonCount">0</div>
            <div class="stat-label">Due Soon</div>
        </div>
        <div class="stat">
            <div class="stat-value" id="completedCount">0</div>
            <div class="stat-label">DoneToday</div>
        </div>
    </div>

    <div class="chore-list" id="choreList"></div>

    <!-- Add Event Modal -->
    <div id="addEventModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">Add New Chore</div>
            <form id="eventForm">
                <div class="form-group">
                    <label class="form-label">Chore Name</label>
                    <input type="text" id="eventJob" class="form-input" required>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label class="form-label">Floor_Location</label>
                        <input type="text" id="eventLocation" class="form-input" required>
                    </div>
                    <div class="form-group">
                        <label class="form-label">Sub-Location</label>
                        <input type="text" id="eventSubLocation" class="form-input" required>
                    </div>
                </div>

                <div class="form-row">
                    <div class="form-group">
                        <label class="form-label">Duration (minutes)</label>
                        <input type="number" id="eventDuration" class="form-input" min="1" value="30" required>
                    </div>
                    <div class="form-group">
                        <label class="form-label">Frequency (per week)</label>
                        <input type="number" id="eventFrequency" class="form-input" min="0.01" step="0.01" value="1" required>
                    </div>
                </div>

                <div class="form-group">
                    <label class="form-label">Frequency Description</label>
                    <input type="text" id="eventVerboseFreq" class="form-input" placeholder="e.g., Weekly, Daily, Monthly">
                </div>

                <div class="form-group">
                    <label class="form-label">When can this be done?</label>
                    <div class="checkbox-group">
                        <label class="checkbox-label">
                            <input type="checkbox" id="eventWeekday" checked>
                            Weekdays
                        </label>
                        <label class="checkbox-label">
                            <input type="checkbox" id="eventWeekend" checked>
                            Weekends
                        </label>
                    </div>
                </div>

                <div class="form-group">
                    <label class="form-label">Specific Days (optional)</label>
                    <div class="day-mask-group">
                        <div class="day-checkbox">
                            <input type="checkbox" id="dayMon" value="1">
                            <label for="dayMon">Mon</label>
                        </div>
                        <div class="day-checkbox">
                            <input type="checkbox" id="dayTue" value="1">
                            <label for="dayTue">Tue</label>
                        </div>
                        <div class="day-checkbox">
                            <input type="checkbox" id="dayWed" value="1">
                            <label for="dayWed">Wed</label>
                        </div>
                        <div class="day-checkbox">
                            <input type="checkbox" id="dayThu" value="1">
                            <label for="dayThu">Thu</label>
                        </div>
                        <div class="day-checkbox">
                            <input type="checkbox" id="dayFri" value="1">
                            <label for="dayFri">Fri</label>
                        </div>
                        <div class="day-checkbox">
                            <input type="checkbox" id="daySat" value="1">
                            <label for="daySat">Sat</label>
                        </div>
                        <div class="day-checkbox">
                            <input type="checkbox" id="daySun" value="1">
                            <label for="daySun">Sun</label>
                        </div>
                    </div>
                </div>

                <div class="button-group">
                    <button type="button" class="btn-secondary" onclick="closeAddEventModal()">Cancel</button>
                    <button type="submit" class="btn-primary">Add Event</button>
                </div>
            </form>
        </div>
    </div>


    <input type="file" id="fileInput" accept=".json">

    <script>
        const CSV_DATA = `id,location,subLocation,job,duration,weeklyFrequency,verboseFrequency,weekday,weekend,dayMask,
1,3rdBath,Shower,RemoveTrash,2,2,Almost Daily,1,1,1101101
2,3rdBath,Shower,Scrub/Clean,9,7,Weekly,1,1,1000000
3,3rdBath,Toilet,Disinfect/Wash,5,7,Weekly,1,1,1000000
4,3rdBath,Toilet,Wipe/Clean,5,3,Twice Weekly,1,1,1001000
5,3rdBath,Toilet,Scrub/Clean,5,14,BiWeekly,1,1,
6,3rdBath,Toilet,FillToiletPaper,2,7,Weekly,1,1,1000000
7,3rdBath,Litter,RemoveTrash,2,7,Weekly,1,1,1000000
8,3rdBath,Litter,Clean/Sweep,5,7,Weekly,1,1,1000000
9,3rdBath,Litter,Sweep/Mop,10,14,BiWeekly,1,1,
10,3rdBath,Litter,Mop/Disinfect,14,28,Monthly,1,1,
11,3rdBath,Litter,Sweep,5,7,Weekly,1,1,1000000
12,3rdBath,Litter,ScoopDaPoop,7,1,Daily,1,1,1111111
13,3rdBath,Counter,RemoveTrash,2,2,Almost Daily,1,1,
14,3rdBath,Counter,Clean/Wipe,4,7,Weekly,1,1,1000000
15,3rdBath,Counter,Wipe/Disinfect,5,14,BiWeekly,1,1,
16,3rdBath,Counter,RemoveLaundry,2,1,Daily,1,1,1111111
17,3rdBath,Counter,Straighten/FindHomes,2,2,Almost Daily,1,1,1101101
18,3rdBath,Sink,Clean/Wipe,4,7,Weekly,1,1,1000000
19,3rdBath,Sink,Scrub/Disinfect,5,28,Monthly,1,1,
20,3rdBath,Mirror,Clean/Wipe,4,7,Weekly,1,1,1000000
21,3rdBath,Laundry,RemoveDirtyClothes,2,1,Daily,1,1,1111111
22,3rdBath,Counter,Wash Towels,17,14,BiWeekly,1,1,
23,3rdBath,Counter,HangTowels,2,14,BiWeekly,1,1,
24,3rdBath,Floor,RemoveTrash,2,2,Almost Daily,1,1,1101101
25,3rdBath,Floor,RemoveLaundry,2,2,Almost Daily,1,1,1101101
26,3rdBath,Floor,Sweep,4,2,Almost Daily,1,1,1101101
27,3rdBath,Floor,Sweep/Mop,9,7,Weekly,1,1,
28,3rdBath,Floor,Mop/Disinfect,10,14,BiWeekly,1,1,
29,3rdBath,Floor,Scrub/Mop,14,28,Monthly,1,1,
30,3rdBath,GarbageCan,RemoveTrash,2,7,Weekly,1,1,1000000
31,3rdBath,GarbageCan,Clean/Disinfect,4,56,BiMonthly,1,1,
32,Bathtub,,Clean/Disinfect,5,14,BiWeekly,1,1,
33,2ndBathroom,Toilet,Disinfect/Wash seat,5,14,BiWeekly,1,1,
34,2ndBathroom,Toilet,Wipe/Clean outside,5,7,Weekly,1,1,1000000
35,2ndBathroom,Toilet,Scrub/Clean bowl,5,28,Monthly,1,1,
36,2ndBathroom,Toilet,FillToiletPaper,5,7,Weekly,1,1,1000000
37,2ndBathroom,Floor,Sweep,4,1,Daily,1,1,1111111
38,2ndBathroom,Floor,Sweep/Mop,9,14,BiWeekly,1,1,
39,2ndBathroom,Floor,Mop/Disinfect,12,14,BiWeekly,1,1,
40,2ndBathroom,Sink,WipeClean,4,7,Weekly,1,1,1000000
41,2ndBathroom,Sink,Scrub/Disinfect,7,14,BiWeekly,1,1,
42,2ndBathroom,GarbageCan,RemoveTrash,2,7,Weekly,1,1,1000000
43,2ndBathroom,GarbageCan,Clean/Disinfect,5,28,Monthly,1,1,
44,2ndBathroom,Litter,RemoveTrash,2,1,Daily,1,1,1111111
45,2ndBathroom,Litter,Clean/Sweep,4,7,Weekly,1,1,1000000
46,2ndBathroom,Litter,Sweep/Mop,9,14,BiWeekly,1,1,
47,2ndBathroom,Litter,Mop/Disinfect,10,28,Monthly,1,1,
48,2ndBathroom,Litter,Sweep,4,2,Almost Daily,1,1,1101101
49,2ndBathroom,Litter,ScoopDaPoop,7,1,Daily,1,1,1111111
50,2ndBathroom,Litter,Scrub/Clean,14,56,BiMonthly,1,1,
51,2ndBathroom,Mirror,Clean/Wipe,4,7,Weekly,1,1,1000000
52,1stBathroom,Toilet,Disinfect/Wash,7,7,Weekly,1,1,1000000
53,1stBathroom,Toilet,Wipe/Clean,7,7,Weekly,1,1,1000000
54,1stBathroom,Toilet,Scrub/Clean,2,14,BiWeekly,1,1,
55,1stBathroom,Toilet,FillToiletPaper,7,7,Weekly,1,1,1000000
56,1stBathroom,Sink,WipeClean,7,7,Weekly,1,1,1000000
57,1stBathroom,Sink,Scrub/Disinfect,7,14,BiWeekly,1,1,
58,1stBathroom,Floor,Sweep,4,1,Daily,1,1,1111111
59,1stBathroom,Floor,Sweep/Mop,9,7,Weekly,1,1,1000000
60,1stBathroom,Floor,Mop/Disinfect,9,14,BiWeekly,1,1,
61,1stBathroom,Litter,RemoveTrash,2,7,Weekly,1,1,1000000
62,1stBathroom,Litter,Clean/Sweep,5,2,Almost Daily,1,1,1101101
63,1stBathroom,Litter,Sweep/Mop,5,14,BiWeekly,1,1,
64,1stBathroom,Litter,Mop/Disinfect,9,28,Monthly,1,1,
65,1stBathroom,Litter,Sweep,5,2,Almost Daily,1,1,1101101
66,1stBathroom,Litter,ScoopDaPoop,7,1,Daily,1,1,1111111
67,1stBathroom,Litter,Scrub/Clean,14,56,BiMonthly,1,1,
68,1stBathroom,Mirror,Clean/Wipe,4,7,Weekly,1,1,1000000
69,Kitchen,Floor,Sweep,4,2,Almost Daily,1,1,1101101
70,Kitchen,Floor,Sweep/Mop,9,7,Weekly,1,1,1000000
71,Kitchen,Floor,Mop/Disinfect,12,14,BiWeekly,1,1,
72,Kitchen,Floor,RemoveTrash,2,1,Daily,1,1,1111111
73,Kitchen,Floor,RemoveRecyclables,4,1,Daily,1,1,1111111
74,Kitchen,CounterBySink,RemoveDebris,2,1,Daily,1,1,1111111
75,Kitchen,CounterBySink,Wipe/Clean,4,1,Daily,1,1,1111111
76,Kitchen,CounterBySink,Wipe/Disinfect,5,7,Weekly,1,1,1000000
77,Kitchen,CounterBySink,Scrub/Disinfect,7,14,BiWeekly,1,1,
78,Kitchen,Counter,RemoveDebris,2,1,Daily,1,1,1111111
79,Kitchen,Counter,Wipe/Clean,4,1,Daily,1,1,1111111
80,Kitchen,Counter,Wipe/Disinfect,5,7,Weekly,1,1,1000000
81,Kitchen,Counter,Scrub/Disinfect,7,14,BiWeekly,1,1,
82,Kitchen,CounterByStove,RemoveDebris,2,1,Daily,1,1,1111111
83,Kitchen,CounterByStove,Wipe/Clean,4,1,Daily,1,1,1111111
84,Kitchen,CounterByStove,Wipe/Disinfect,5,7,Weekly,1,1,1000000
85,Kitchen,CounterByStove,Scrub/Disinfect,7,14,BiWeekly,1,1,
86,Kitchen,Sink,WashDishes,4,1,Daily,1,1,1111111
87,Kitchen,Sink,PutAwayDishes,4,1,Daily,1,1,1111111
88,Kitchen,Sink,WipeClean,4,1,Daily,1,1,1111111
89,Kitchen,Sink,Scrub/Disinfect,4,7,Weekly,1,1,1000000
90,Kitchen,GarbageCan,RemoveTrash,4,1,Daily,1,1,1111111
91,Kitchen,GarbageCan,Clean/Disinfect,7,28,Monthly,1,1,
92,Kitchen,Recycleing,RemoveRecycling,2,7,Weekly,1,1,1000000
93,Kitchen,Table,RemoveTrash,2,2,Almost Daily,1,1,1101101
94,Kitchen,Table,RemoveRecycling,2,2,Almost Daily,1,1,1101101
95,Kitchen,Table,Wipe/Disinfect,4,14,BiWeekly,1,1,
96,Kitchen,Dishwasher,Straighten/FindHomes,2,1,Daily,1,1,1111111
97,Kitchen,Dishwasher,RemoveTrash,2,1,Daily,1,1,1111111
98,Kitchen,Dishwasher,WipeClean,2,7,Weekly,1,1,1000000
99,Kitchen,DishRack,Straighten/FindHomes,2,1,Daily,1,1,1111111
100,Kitchen,DishRack,WashLaundry,17,14,BiWeekly,1,1,
101,Kitchen,DishRack,WipeClean,2,1,Daily,1,1,1111111
102,Kitchen,Microwave,WipeClean,2,7,Weekly,1,1,1000000
103,Kitchen,Microwave,Scrub/Disinfect,7,14,BiWeekly,1,1,
104,Kitchen,Refridgerator,RemoveTrash,4,7,Weekly,1,1,1000000
105,Kitchen,Refridgerator,Scrub/Disinfect,5,28,Monthly,1,1,
106,Kitchen,Refridgerator,WashClean,9,14,BiWeekly,1,1,
107,Kitchen,Refridgerator,Remove Old/Empties,2,7,Weekly,1,1,1000000
108,Kitchen,ToasterOven,RemoveTrash,4,7,Weekly,1,1,1000000
109,Kitchen,ToasterOven,ScrubClean,5,7,Weekly,1,1,1000000
110,Kitchen,ToasterOven,WashClean,4,14,BiWeekly,1,1,
111,3rdHallway,Floor,Vacume,9,7,Weekly,1,1,1000000
112,3rdHallway,Floor,RemoveTrash,2,1,Daily,1,1,1111111
113,3rdHallway,Baseboards,SweepClean,2,7,Weekly,1,1,1000000
114,3rdHallway,Baseboards,Wipe/Scrub,7,56,BiMonthly,1,1,
115,3rdHallway,Nerdlounge,RemoveTrash,2,7,Weekly,1,1,1000000
116,3rdHallway,Nerdlounge,Vacume,9,7,Weekly,1,1,1000000
117,3rdHallway,BackCloset,RemoveTrash,2,7,Weekly,1,1,1000000
118,3rdHallway,BackCloset,Vacume,9,7,Weekly,1,1,1000000
119,2ndHallway,Floor,RemoveTrash,2,1,Daily,1,1,1111111
120,2ndHallway,Floor,SweepClean,4,2,Almost Daily,1,1,1101101
121,2ndHallway,Floor,Mop/Disinfect,9,14,BiWeekly,1,1,
122,2ndHallway,Baseboards,SweepClean,4,7,Weekly,1,1,1000000
123,2ndHallway,Baseboards,Mop/Disinfect,9,14,BiWeekly,1,1,
124,Stairway,Floor,RemoveTrash,2,1,Daily,1,1,1111111
125,Stairway,Floor,VacumeLanding,7,7,Weekly,1,1,1000000
126,Stairway,Floor,VacumeStairs,14,14,BiWeekly,1,1,
127,Stairway,Baseboards,SweepClean,4,7,Weekly,1,1,1000000
128,Stairway,Baseboards,Mop/Disinfect,7,14,BiWeekly,1,1,
129,Stairway,Window,Vacume Clean,2,14,BiWeekly,1,1,
130,Stairway,Window,WashClean,5,56,BiMonthly,1,1,
131,Stairway,Floor,SweepClean,4,7,Weekly,1,1,1000000
132,Stairway,Floor,Mop/Disinfect,9,14,BiWeekly,1,1,
133,Stairway,baseboards,SweepClean,4,7,Weekly,1,1,1000000
134,Stairway,baseboards,Wipe/Mop,9,14,BiWeekly,1,1,
135,Stairway,Window,Vacume Clean,2,28,Monthly,1,1,
136,Stairway,Window,WashClean,7,28,Monthly,1,1,
137,Stairway,Floor,SweepClean,4,7,Weekly,1,1,1000000
138,Stairway,Floor,Mop/Disinfect,9,14,BiWeekly,1,1,
139,Stairway,BaseBoards,SweepClean,4,7,Weekly,1,1,1000000
140,Stairway,BaseBoards,Wipe/Mop,7,14,BiWeekly,1,1,
141,Stairway,Ceiling,Vacume/Sweep,4,14,BiWeekly,1,1,
142,Stairway,Ceiling,WipeClean,10,56,BiMonthly,1,1,
143,LivingRoom,Floor,RemoveTrash,4,2,Almost Daily,1,1,1101101
144,LivingRoom,Floor,Straighten&Vacume,7,7,Weekly,1,1,1000000
145,LivingRoom,Floor,Wash/Disinfiect,19,0,Yearly,1,1,
146,LivingRoom,Table,RemoveTrash,2,2,Almost Daily,1,1,1101101
147,LivingRoom,Table,WipeClean,2,7,Weekly,1,1,1000000
148,LivingRoom,Table,Scrub/Disinfect,4,14,BiWeekly,1,1,
149,LivingRoom,Table,Straighten/FindHomes,2,2,Almost Daily,1,1,1101101
150,LivingRoom,Under/behind Couchs,RemoveTrash,9,14,BiWeekly,1,1,
151,LivingRoom,Under/behind Couchs,Vacume/Find Homes,9,14,BiWeekly,1,1,
152,LivingRoom,KittyCabana,Straighten/FindHomes,2,7,Weekly,1,1,1000000
153,LivingRoom,KittyCabana,RemoveTrash,2,7,Weekly,1,1,1000000
154,LivingRoom,KittyCabana,Vacume,4,7,Weekly,1,1,1000000
155,LivingRoom,OpiumDen,RemoveTrash,2,7,Weekly,1,1,1000000
156,LivingRoom,OpiumDen,Straighten&Vacume,4,7,Weekly,1,1,1000000
157,LivingRoom,MediCentre,Straighten/FindHomes,2,14,BiWeekly,1,1,
158,LivingRoom,MediCentre,WipeClean,2,14,BiWeekly,1,1,
159,FrontDoor,Floor,RemoveTrash,2,2,Almost Daily,1,1,1101101
160,FrontDoor,Floor,SweepClean,4,7,Weekly,1,1,1000000
161,FrontDoor,Floor,Mop/Disinfect,9,28,Monthly,1,1,
162,FrontDoor,innerDoorGlass,WipeClean,7,56,BiMonthly,1,1,
163,FrontDoor,woodenDoorGlass,WipeClean,7,56,BiMonthly,1,1,
164,FrontDoor,OuterDoorGlass,WipeClean,7,56,BiMonthly,1,1,
165,FrontDoor,Table,WipeClean,2,56,BiMonthly,1,1,
166,FrontDoor,Ceiling,Wipe/Sweep,4,56,BiMonthly,1,1,
167,BackDoor,Floor,RemoveTrash,4,7,Weekly,1,1,1000000
168,BackDoor,Floor,Vacume/Sweep,7,7,Weekly,1,1,1000000
169,BackDoor,Floor,Mop/Disinfect,10,56,BiMonthly,1,1,
170,BackDoor,InnerDoorGlass,WipeClean,7,56,BiMonthly,1,1,
171,BackDoor,OuterDoorGlass,WipeClean,7,56,BiMonthly,1,1,
172,BackDoor,TopofCupboards,RemoveTrash,2,7,Weekly,1,1,1000000
173,BackDoor,TopofCupboards,WipeClean,4,56,BiMonthly,1,1,
174,BackDoor,Closet,Straighten/FindHomes,4,14,BiWeekly,1,1,
175,BackDoor,Closet,Vacume/Sweep,4,7,Weekly,1,1,1000000
176,BackDoor,RecycleingWall,RemoveRecycling,4,7,Weekly,1,1,1000000
177,BackDoor,Ceiling,Wipe/Sweep,4,56,BiMonthly,1,1,
178,DiningRoom,Floor,RemoveTrash,2,1,Daily,1,1,1111111
179,DiningRoom,Floor,Straighten&Sweep,4,2,Almost Daily,1,1,1101101
180,DiningRoom,Floor,Mop/Disinfect,7,7,Weekly,1,1,1000000
181,DiningRoom,Table,RemoveTrash,2,1,Daily,1,1,1111111
182,DiningRoom,Table,Straighten/FindHomes,2,2,Almost Daily,1,1,1101101
183,DiningRoom,Table,WipeClean,4,7,Weekly,1,1,1000000
184,DiningRoom,Table,Scrub/Disinfect,5,14,BiWeekly,1,1,
185,DiningRoom,BarTop,RemoveTrash,2,7,Weekly,1,1,1000000
186,DiningRoom,BarTop,Straighten&Wipe,2,7,Weekly,1,1,1000000
187,DiningRoom,CornerHutchGlass,WipeClean,2,56,BiMonthly,1,1,
188,DiningRoom,CornerHutchGlass,Vacume/Sweep,2,56,BiMonthly,1,1,
189,DiningRoom,Hutch,RemoveTrash,2,56,BiMonthly,1,1,
190,DiningRoom,Hutch,Straighten&Wipe,2,56,BiMonthly,1,1,
191,DiningRoom,StevensTable,Straighten&Wipe,2,7,Weekly,1,1,1000000
192,DiningRoom,KitchenDoorGlass,WipeClean,2,56,BiMonthly,1,1,
193,DiningRoom,Mirror,WipeClean,2,56,BiMonthly,1,1,
194,DiningRoom,Windows,WipeClean,2,56,BiMonthly,1,1,
195,DiningRoom,Windows,Vacume/Sweep,2,56,BiMonthly,1,1,
196,Sunroom,Floor,RemoveTrash,4,7,Weekly,1,1,1000000
197,Sunroom,Floor,Straighten&Sweep,5,7,Weekly,1,1,1000000
198,Sunroom,Floor,Mop/Disinfect,9,28,Monthly,1,1,
199,Sunroom,Windows,WipeClean,5,56,BiMonthly,1,1,
200,Sunroom,Windows,Vacume/Sweep,5,56,BiMonthly,1,1,
201,Sunroom,Bed,Straighten/FindHomes,5,7,Weekly,1,1,1000000
202,Sunroom,Bed,WashLaundry,5,14,BiWeekly,1,1,
203,Sunroom,Shelves,Vacume/Sweep,5,7,Weekly,1,1,1000000
204,Sunroom,Shelves,Straighten/FindHomes,5,7,Weekly,1,1,1000000
205,Sunroom,Ceiling,Vacume/Sweep,5,14,BiWeekly,1,1,
206,LivingRoom,Floor,RemoveTrash,5,7,Weekly,1,1,1000000
207,LivingRoom,Floor,Straighten&Sweep,5,7,Weekly,1,1,1000000
208,LivingRoom,Floor,Mop/Disinfect,5,14,BiWeekly,1,1,
209,LivingRoom,SlidingDoorGlass,WipeClean,5,7,Weekly,1,1,1000000
210,LivingRoom,SlidingDoorGlass,Vacume/Sweep,5,56,BiMonthly,1,1,
211,LivingRoom,Windows,WipeClean,5,56,BiMonthly,1,1,
212,LivingRoom,Windows,Vacume/Sweep,5,56,BiMonthly,1,1,
213,LivingRoom,Couch,Straighten&Vacume,5,7,Weekly,1,1,1000000
214,LivingRoom,Couch,WashLaundry,5,14,BiWeekly,1,1,
215,LivingRoom,Fireplace,CleanDisinfect,5,56,BiMonthly,1,1,
216,LivingRoom,Chairs,Straighten&Vacume,5,7,Weekly,1,1,1000000
217,LivingRoom,Chairs,WashLaundry,5,14,BiWeekly,1,1,
218,LivingRoom,Bed,Straighten&Vacume,5,7,Weekly,1,1,1000000
219,LivingRoom,Bed,WashLaundry,5,14,BiWeekly,1,1,
220,LivingRoom,Bed,RemoveTrash,5,1,Daily,1,1,1111111`;

        let chores = [];
        let customEvents = [];
        let completionData = {};
        let searchTerm = '';
        let currentFilter = 'all';
        let collapsedFloors = {};
        let collapsedRooms = {};
        let hasInitialized = false;
        let nextCustomId = 1000; // Start custom events at ID 1000

        function parseCSV(csv) {
            const lines = csv.trim().split('\n');
            const headers = lines[0].split(',');
            return lines.slice(1).map(line => {
                const values = line.split(',');
                return {
                    id: values[0],
                    location: values[1],
                    subLocation: values[2],
                    job: values[3],
                    duration: parseInt(values[4]),
                    weeklyFrequency: parseFloat(values[5]),
                    verboseFrequency: values[6],
                    weekday: values[7],
                    weekend: values[8],
                    dayMask: values[9]
                };
            });
        }

        function getDayMask() {
            const days = ['dayMon', 'dayTue', 'dayWed', 'dayThu', 'dayFri', 'daySat', 'daySun'];
            return days.map(day => document.getElementById(day).checked ? '1' : '0').join('');
        }

        function openAddEventModal() {
            document.getElementById('addEventModal').classList.add('active');
        }

        function closeAddEventModal() {
            document.getElementById('addEventModal').classList.remove('active');
            document.getElementById('eventForm').reset();
        }

        function handleAddEvent(e) {
            e.preventDefault();
            
            const newEvent = {
                id: String(nextCustomId++),
                location: document.getElementById('eventLocation').value,
                subLocation: document.getElementById('eventSubLocation').value,
                job: document.getElementById('eventJob').value,
                duration: parseInt(document.getElementById('eventDuration').value),
                weeklyFrequency: parseFloat(document.getElementById('eventFrequency').value),
                verboseFrequency: document.getElementById('eventVerboseFreq').value || 'Custom',
                weekday: document.getElementById('eventWeekday').checked ? '1' : '0',
                weekend: document.getElementById('eventWeekend').checked ? '1' : '0',
                dayMask: getDayMask(),
                isCustom: true
            };

            customEvents.push(newEvent);
            saveCustomEvents();
            closeAddEventModal();
            renderChores();
        }

        function deleteEvent(eventId) {
            if (confirm('Are you sure you want to delete this event?')) {
                customEvents = customEvents.filter(e => e.id !== eventId);
                delete completionData[eventId];
                saveCustomEvents();
                saveCompletionData();
                renderChores();
            }
        }

        async function saveCustomEvents() {
            try {
                await window.storage.set('customEvents', JSON.stringify(customEvents));
            } catch (error) {
                console.error('Error saving custom events:', error);
            }
        }

        async function loadCustomEvents() {
            try {
                const result = await window.storage.get('customEvents');
                if (result && result.value) {
                    customEvents = JSON.parse(result.value);
                    // Update nextCustomId to avoid conflicts
                    if (customEvents.length > 0) {
                        const maxId = Math.max(...customEvents.map(e => parseInt(e.id)));
                        nextCustomId = Math.max(nextCustomId, maxId + 1);
                    }
                }
            } catch (error) {
                console.error('Error loading custom events:', error);
                customEvents = [];
            }
        }

        async function saveCompletionData() {
            try {
                await window.storage.set('completionData', JSON.stringify(completionData));
                 localStorage.set('completionData', JSON.stringify(completionData));
            } catch (error) {
                console.error('Error saving completion data:', error);
            }
           
            
        }

        async function loadCompletionData() {
            try {
                const result = localStorage.get('completionData');
                
                    completionData = JSON.parse(result.value);
                
            } catch (error) {
                console.error('Error loading completion data:', error);
                completionData = {};
            }
        }

        function markComplete(choreId) {
            const today = new Date().toDateString();
            completionData[choreId] = today;
            saveCompletionData();
            renderChores();
        }

        function getNextDueDate(lastCompleted, weeklyFrequency) {
            if (!lastCompleted) return new Date();
            const last = new Date(lastCompleted);
            const daysToAdd = weeklyFrequency * 24 * 60 * 60 * 1000;
            return new Date(last.getTime() + daysToAdd);
        }

        function getStatus(chore) {
            const lastCompleted = completionData[chore.id];
            const nextDue = getNextDueDate(lastCompleted, chore.weeklyFrequency);
            const now = new Date();
            const daysUntilDue = Math.floor((nextDue.getTime() - now.getTime()) / (1000 * 60 * 60 * 24));

            if (daysUntilDue < 0) return 'overdue';
            if (daysUntilDue <= 2) return 'due-soon';
            return 'good';
        }

        function formatDate(dateString) {
            if (!dateString) return 'Never';
            const date = new Date(dateString);
            const now = new Date();
            const diffTime = Math.abs(now - date);
            const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));

            if (diffDays === 0) return 'Today';
            if (diffDays === 1) return 'Yesterday';
            if (diffDays < 7) return `${diffDays} days ago`;
            if (diffDays < 30) return `${Math.floor(diffDays / 7)} weeks ago`;
            return date.toLocaleDateString();
        }

        function formatNextDue(date) {
            const now = new Date();
            const diffTime = date - now;
            const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));

            if (diffDays < 0) return 'Overdue';
            if (diffDays === 0) return 'Today';
            if (diffDays === 1) return 'Tomorrow';
            if (diffDays < 7) return `In ${diffDays} days`;
            return date.toLocaleDateString();
        }

        function formatDayMask(mask) {
            const days = ['M', 'T', 'W', 'T', 'F', 'S', 'S'];
            return days.map((day, i) => mask[i] === '1' ? day : '-').join(' ');
        }

        function organizeByFloorAndRoom(chores) {
            const organized = {};
            chores.forEach(chore => {
                const floor = getFloor(chore.location);
                if (!organized[floor]) organized[floor] = {};
                const room = chore.subLocation;
                if (!organized[floor][room]) organized[floor][room] = [];
                organized[floor][room].push(chore);
            });
            return organized;
        }


function getFloor(location) {
    if (location === 'New Events') return 'New Events';

    // Get first character for prefix matching
    const firstChar = location.charAt(0).toUpperCase();

    const thirdFloor = ['3rd','Bedroom'];
    const secondFloor = ['2nd','Bathroom', 'Office', 'Hallway'];
    const firstFloor = ['1st','Kitchen', 'Living Room', 'Dining Room', 'Laundry', 'Entryway', 'Garage', 'Yard', 'Windows', 'General'];
    const basement = ['Bsmt','Bmt','Basement'];
    const outside = ['0th','Outside','Garage'];

    // Check for exact matches first (preserves current functionality)
    if (thirdFloor.includes(location)) return '3rd Floor';
    if (secondFloor.includes(location)) return '2nd Floor';
    if (firstFloor.includes(location)) return '1st Floor';
    if (basement.includes(location)) return 'Basement';
    if (outside.includes(location)) return 'Outside';

    // Then check first character/digit
    if (firstChar === '3') return '3rd Floor';
    if (firstChar === '2') return '2nd Floor';
    if (firstChar === '1') return '1st Floor';
    if (firstChar === 'B') return 'Basement';
    if (firstChar === '0') return 'Outside';

    // Default fallback
    return '1st Floor';
}
        function toggleFloor(floor) {
            collapsedFloors[floor] = !collapsedFloors[floor];
            renderChores();
        }

        function toggleRoom(floor, room) {
            const key = `${floor}-${room}`;
            collapsedRooms[key] = !collapsedRooms[key];
            renderChores();
        }

        function expandAll() {
            collapsedFloors = {};
            collapsedRooms = {};
            renderChores();
        }

        function collapseAll() {
            const floors = ['3rd Floor', '2nd Floor', '1st Floor', 'New Events','Basement','Outside'];
            floors.forEach(floor => collapsedFloors[floor] = true);
            renderChores();
        }

        function exportData() {
            const data = {
                completionData,
                customEvents,
                exportDate: new Date().toDateString()
            };
            const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `chore-tracker-backup-${new Date().toDateString().split('T')[0]}.json`;
            a.click();
            URL.revokeObjectURL(url);
        }
function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
}
        function importData() {
            document.getElementById('fileInput').click();
        }
        function openData() {
           document.getElementById('fileInput').click();
        }

        function handleFileImport(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = async (e) => {
                try {
                    const data = JSON.parse(e.target.result);
                    if (data.completionData) {
                        completionData = data.completionData;
                        await saveCompletionData();
                    }
                    if (data.customEvents) {
                        customEvents = data.customEvents;
                        await saveCustomEvents();
                        // Update nextCustomId
                        if (customEvents.length > 0) {
                            const maxId = Math.max(...customEvents.map(e => parseInt(e.id)));
                            nextCustomId = Math.max(nextCustomId, maxId + 1);
                        }
                    }
                    alert('✅ Data imported successfully!');
                    renderChores();
                } catch (error) {
                    alert('❌ Error importing file: ' + error.message);
                }
            };
            reader.readAsText(file);
            event.target.value = '';
        }

        function renderChores() {
            const allChores = [...chores, ...customEvents];
            const filteredChores = allChores.filter(chore => {
                const matchesSearch = !searchTerm ||
                    chore.location.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    chore.job.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    chore.subLocation.toLowerCase().includes(searchTerm.toLowerCase());

                if (currentFilter === 'overdue') {
                    return matchesSearch && getStatus(chore) === 'overdue';
                }

                return matchesSearch;
            });

            const organized = organizeByFloorAndRoom(filteredChores);

            // Update stats
            const today = new Date().toDateString();
            const completedToday = Object.values(completionData).filter(date =>
                new Date(date).toDateString() === today
            ).length;

            document.getElementById('overdueCount').textContent =
                allChores.filter(c => getStatus(c) === 'overdue').length;
            document.getElementById('dueSoonCount').textContent =
                allChores.filter(c => getStatus(c) === 'due-soon').length;
            document.getElementById('completedCount').textContent = completedToday;

            const choreList = document.getElementById('choreList');

            if (filteredChores.length === 0 && customEvents.length === 0) {
                choreList.innerHTML = `
                    <div class="empty-state">
                        <div class="empty-state-icon">✨</div>
                        <p>No chores to display</p>
                    </div>
                `;
                return;
            }

            const floors = ['3rd Floor', '2nd Floor', '1st Floor','New Events','Basement','Outside'];

            choreList.innerHTML = floors.map(floor => {
                if (floor === 'New Events') {
                    const isFloorCollapsed = collapsedFloors[floor];
                    const newEventsData = organized[floor] || {};
                    const eventCount = Object.values(newEventsData).flat().length;
                    const eventOverdueCount = Object.values(newEventsData).flat().filter(c => getStatus(c) === 'overdue').length;

                    return `
                        <div class="floor-section">
                            <div class="floor-header new-events" onclick="toggleFloor('${floor}')">
                                <div class="floor-title">
                                    <span>🎯 ${floor}</span>
                                    <span class="floor-badge">${eventCount} events${eventOverdueCount > 0 ? ` • ${eventOverdueCount} overdue` : ''}</span>
                                </div>
                                <span class="floor-chevron ${isFloorCollapsed ? 'collapsed' : ''}">▼</span>
                            </div>
                            <div class="floor-content ${isFloorCollapsed ? 'collapsed' : ''}">
                                <div class="add-event-section">
                                    <button class="add-event-btn" onclick="openAddEventModal()">
                                        <span style="font-size: 24px;">➕</span>
                                        <span>Add New Chore</span>
                                    </button>
                                </div>
                                ${Object.keys(newEventsData).map(room => {
                                    const roomChores = newEventsData[room];
                                    const roomOverdueCount = roomChores.filter(c => getStatus(c) === 'overdue').length;
                                    const isRoomCollapsed = collapsedRooms[`${floor}-${room}`];

                                    return `
                                        <div class="room-section">
                                            <div class="room-header" onclick="toggleRoom('${floor}', '${room}')">
                                                <div class="room-title">
                                                    <span>${room}</span>
                                                    <span class="room-badge">${roomChores.length} events${roomOverdueCount > 0 ? ` • ${roomOverdueCount} overdue` : ''}</span>
                                                </div>
                                                <span class="room-chevron ${isRoomCollapsed ? 'collapsed' : ''}">▼</span>
                                            </div>
                                            <div class="room-content ${isRoomCollapsed ? 'collapsed' : ''}">
                                                ${roomChores.map(chore => {
                                                    const status = getStatus(chore);
                                                    const lastCompleted = completionData[chore.id];
                                                    const nextDue = getNextDueDate(lastCompleted, chore.weeklyFrequency);
                                                    const isCompletedToday = lastCompleted &&
                                                        new Date(lastCompleted).toDateString() === new Date().toDateString();

                                                    return `
                                                        <div class="chore-card ${status}">
                                                            <div class="chore-header">
                                                                <div>
                                                                    <div class="chore-title">~ ${chore.subLocation} ~ ${chore.location} ~</br>~ ${chore.job} ~</div>
                                                                </div>
                                                                <span class="frequency-badge">${chore.verboseFrequency}</span>
                                                            </div>

                                                            <div class="chore-info">
                                                                <div class="info-item">
                                                                    <span class="info-label">Last Done</span>
                                                                    <span class="info-value">${formatDate(lastCompleted)}</span>
                                                                </div>
                                                                <div class="info-item">
                                                                    <span class="info-label">Next Due</span>
                                                                    <span class="info-value">${formatNextDue(nextDue)}</span>
                                                                </div>
                                                                <div class="info-item">
                                                                    <span class="info-label">Duration</span>
                                                                    <span class="info-value">${chore.duration} min</span>
                                                                </div>
                                                                <div class="info-item">
                                                                    <span class="info-label">Status</span>
                                                                    <span class="status-badge status-${status}">
                                                                        ${status === 'overdue' ? 'Overdue' : status === 'due-soon' ? 'Due Soon' : 'On Track'}
                                                                    </span>
                                                                </div>
                                                                <div class="info-item">
                                                                    <span class="info-label">Weekday</span>
                                                                    <span class="info-value">${chore.weekday === '1' ? 'Yes' : 'No'}</span>
                                                                </div>
                                                                <div class="info-item">
                                                                    <span class="info-label">Weekend</span>
                                                                    <span class="info-value">${chore.weekend === '1' ? 'Yes' : 'No'}</span>
                                                                </div>
                                                                <div class="info-item" style="grid-column: 1 / -1;">
                                                                    <span class="info-label2">Schedule (Mon-Sun)</span>
                                                                    <span class="info-value">${formatDayMask(chore.dayMask)}</span>
                                                                </div>
                                                            </div>

                                                            <button class="complete-btn ${isCompletedToday ? 'completed' : ''}"
                                                                    onclick="markComplete('${chore.id}')">
                                                                ${isCompletedToday ? '✓ Completed Today' : 'Mark Complete'}
                                                            </button>
                                                            ${chore.isCustom ? `
                                                                <button class="delete-btn" onclick="deleteEvent('${chore.id}')">
                                                                    🗑️ Delete Event
                                                                </button>
                                                            ` : ''}
                                                        </div>
                                                    `;
                                                }).join('')}
                                            </div>
                                        </div>
                                    `;
                                }).join('')}
                            </div>
                        </div>
                    `;
                }

                if (!organized[floor]) return '';

                const rooms = organized[floor];
                const floorChoreCount = Object.values(rooms).flat().length;
                const floorOverdueCount = Object.values(rooms).flat().filter(c => getStatus(c) === 'overdue').length;
                const isFloorCollapsed = collapsedFloors[floor];

                return `
                    <div class="floor-section">
                        <div class="floor-header" onclick="toggleFloor('${floor}')">
                            <div class="floor-title">
                                <span>${floor}</span>
                                <span class="floor-badge">${floorChoreCount} chores${floorOverdueCount > 0 ? ` • ${floorOverdueCount} overdue` : ''}</span>
                            </div>
                            <span class="floor-chevron ${isFloorCollapsed ? 'collapsed' : ''}">▼</span>
                        </div>
                        <div class="floor-content ${isFloorCollapsed ? 'collapsed' : ''}">
                            ${Object.keys(rooms).map(room => {
                                const roomChores = rooms[room];
                                const roomOverdueCount = roomChores.filter(c => getStatus(c) === 'overdue').length;
                                const isRoomCollapsed = collapsedRooms[`${floor}-${room}`];

                                return `
                                    <div class="room-section">
                                        <div class="room-header" onclick="toggleRoom('${floor}', '${room}')">
                                            <div class="room-title">
                                                <span>${room}</span>
                                                <span class="room-badge">${roomChores.length} chores${roomOverdueCount > 0 ? ` • ${roomOverdueCount} overdue` : ''}</span>
                                            </div>
                                            <span class="room-chevron ${isRoomCollapsed ? 'collapsed' : ''}">▼</span>
                                        </div>
                                        <div class="room-content ${isRoomCollapsed ? 'collapsed' : ''}">
                                            ${roomChores.map(chore => {
                                                const status = getStatus(chore);
                                                const lastCompleted = completionData[chore.id];
                                                const nextDue = getNextDueDate(lastCompleted, chore.weeklyFrequency);
                                                const isCompletedToday = lastCompleted &&
                                                    new Date(lastCompleted).toDateString() === new Date().toDateString();

                                                return `
                                                    <div class="chore-card ${status}">
                                                        <div class="chore-header">
                                                            <div>
                                                                <div class="chore-title">~ ${chore.job} : ${chore.subLocation} ~</div>
                                                            </div>
                                                            <span class="frequency-badge">${chore.location}  ${chore.verboseFrequency}</span>

                                                        </div>

                                                        <div class="chore-info">
                                                            <div class="info-item">
                                                                <span class="info-label">Last Done</span>
                                                                <span class="info-value">${formatDate(lastCompleted)}</span>
                                                            </div>
                                                            <div class="info-item">
                                                                <span class="info-label">Next Due</span>
                                                                <span class="info-value">${formatNextDue(nextDue)}</span>
                                                            </div>
                                                            <div class="info-item">
                                                                <span class="info-label">Duration</span>
                                                                <span class="info-value">${chore.duration} min</span>
                                                            </div>
                                                            <div class="info-item">
                                                                <span class="info-label">Status</span>
                                                                <span class="status-badge status-${status}">
                                                                    ${status === 'overdue' ? 'Overdue' : status === 'due-soon' ? 'Due Soon' : 'On Track'}
                                                                </span>
                                                            </div>
                                                            <div class="info-item">
                                                                <span class="info-label">Weekday</span>
                                                                <span class="info-value">${chore.weekday === '1' ? 'Yes' : 'No'}</span>

                                                                <span class="info-label">Weekend</span>
                                                                <span class="info-value">${chore.weekend === '1' ? 'Yes' : 'No'}</span>
                                                            </div>
                                                           <button class="complete-btn ${isCompletedToday ? 'completed' : ''}"
                                                                onclick="markComplete('${chore.id}')">
                                                            ${isCompletedToday ? '✓ Completed Today' : 'Mark Complete'}
                                                        </button>
                                                           <div class="info-item" style="grid-column: 1 / -1;">
                                                                <span class="info-label2">${formatDayMask(chore.dayMask)}</span>
                                                            </div>
                                                        </div>


                                                    </div>
                                                `;
                                            }).join('')}
                                        </div>
                                    </div>
                                `;
                            }).join('')}
                        </div>
                    </div>
                `;
            }).join('');
        }

        // Initialize
        async function init() {
            chores = parseCSV(CSV_DATA);
            await loadCompletionData();
            await loadCustomEvents();
            hasInitialized = true;
            openData();
            renderChores();

        }


        // Event listeners
        document.getElementById('searchInput').addEventListener('input', (e) => {
            searchTerm = e.target.value;
            expandAll();
        });

        document.getElementById('filterOverdue').addEventListener('click', () => {
            currentFilter = 'overdue';
            document.getElementById('filterOverdue').classList.add('active');
            document.getElementById('filterAll').classList.remove('active');
            collapseAll();
        });

        document.getElementById('filterAll').addEventListener('click', () => {
            currentFilter = 'all';
            document.getElementById('filterAll').classList.add('active');
            document.getElementById('filterOverdue').classList.remove('active');
            collapseAll();
        });

        document.getElementById('expandAll').addEventListener('click', expandAll);
        document.getElementById('collapseAll').addEventListener('click', collapseAll);
        document.getElementById('exportData').addEventListener('click', exportData);
        document.getElementById('importData').addEventListener('click', importData);
        document.getElementById('fileInput').addEventListener('change', handleFileImport);
        document.getElementById('eventForm').addEventListener('submit', handleAddEvent);

        document.getElementById('clearButton').addEventListener('click', () => {
        document.getElementById('searchInput').value = '';
        searchTerm = '';
        renderChores();
        });


        // Start app
        init();
    </script>
</body>
</html>
