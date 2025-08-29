# Court-CMS.
Easily Find out Court Percentage &amp; Pendency 
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Court Case Management System</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #e0e7ff 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 20px;
            color: #333;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            background: #1a237e;
            color: white;
            padding: 15px 20px;
            border-radius: 10px 10px 0 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            font-size: 24px;
            color: #ffd54f;
        }
        
        .controls {
            display: flex;
            gap: 10px;
        }
        
        .btn {
            padding: 8px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 5px;
            transition: all 0.3s;
        }
        
        .btn-primary {
            background: #1565c0;
            color: white;
        }
        
        .btn-primary:hover {
            background: #0d47a1;
        }
        
        .btn-success {
            background: #2e7d32;
            color: white;
        }
        
        .btn-success:hover {
            background: #1b5e20;
        }
        
        .btn-danger {
            background: #c62828;
            color: white;
        }
        
        .btn-danger:hover {
            background: #b71c1c;
        }
        
        .btn-warning {
            background: #ef6c00;
            color: white;
        }
        
        .btn-warning:hover {
            background: #e65100;
        }
        
        .court-info {
            background: white;
            padding: 20px;
            border-radius: 0 0 10px 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }
        
        .court-name {
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 15px;
            color: #1a237e;
            text-align: center;
            padding: 10px;
            border: 1px dashed #7986cb;
            background-color: #e8eaf6;
            border-radius: 5px;
        }
        
        .date-display {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            background: #e3f2fd;
            padding: 10px 15px;
            border-radius: 5px;
            font-weight: 500;
            color: #1565c0;
            border: 1px solid #bbdefb;
        }
        
        .dashboard {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .data-table {
            background: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            border: 1px solid #e0e0e0;
        }
        
        .data-table h2 {
            margin-bottom: 15px;
            color: #1a237e;
            padding-bottom: 10px;
            border-bottom: 2px solid #e0e0e0;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        th, td {
            padding: 12px 15px;
            text-align: center;
            border-bottom: 1px solid #ddd;
        }
        
        th {
            background-color: #f5f5f5;
            font-weight: 600;
            color: #1a237e;
        }
        
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        
        tr:hover {
            background-color: #f5f5f5;
        }
        
        input[type="number"] {
            width: 60px;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            text-align: center;
            font-weight: bold;
        }
        
        .case-note {
            font-size: 12px;
            color: #666;
            text-align: left;
            padding: 4px 0;
            font-style: italic;
        }
        
        .summary {
            display: none;
        }
        
        .target-message {
            background: #e8f5e9;
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
            border-left: 4px solid #2e7d32;
            color: #1b5e20;
        }
        
        .report {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            margin-top: 30px;
            display: none;
            border: 1px solid #e0e0e0;
        }
        
        .report-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .report-header h1 {
            color: #1a237e;
            margin-bottom: 10px;
        }
        
        .report-header p {
            color: #666;
            font-size: 18px;
        }
        
        .report-table {
            margin-bottom: 30px;
            width: 100%;
        }
        
        .report-table h3 {
            margin-bottom: 15px;
            color: #1a237e;
            padding-bottom: 10px;
            border-bottom: 2px solid #e0e0e0;
        }
        
        .signature {
            margin-top: 50px;
            text-align: center;
        }
        
        .signature p {
            margin-bottom: 5px;
        }
        
        .signature-line {
            margin-top: 60px;
            border-top: 1px solid #333;
            width: 250px;
            margin: 0 auto;
            padding-top: 5px;
        }
        
        .action-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
        }
        
        .achieved-badge {
            background-color: #2e7d32;
            color: white;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 14px;
            margin-left: 10px;
        }
        
        .edit-court-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }
        
        .modal-content {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            width: 500px;
            max-width: 90%;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .modal-header h2 {
            color: #1a237e;
            margin: 0;
        }
        
        .close-modal {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: #666;
        }
        
        .court-name-input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
            margin-bottom: 20px;
        }
        
        .modal-actions {
            display: flex;
            justify-content: flex-end;
            gap: 10px;
        }
        
        .save-notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #2e7d32;
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            display: none;
            z-index: 1000;
        }
        
        /* New styles for the updates */
        .percentage-bold {
            font-weight: bold;
        }
        
        .report-table table {
            border-left: 1px solid #ddd;
            border-right: 1px solid #ddd;
        }
        
        .report-table table th, 
        .report-table table td {
            border-left: 1px solid #ddd;
            border-right: 1px solid #ddd;
        }
        
        .report-bold {
            font-weight: bold;
        }
        
        @media print {
            body * {
                visibility: hidden;
            }
            .report, .report * {
                visibility: visible;
            }
            .report {
                position: absolute;
                left: 0;
                top: 0;
                width: 100%;
            }
            .no-print {
                display: none;
            }
        }
        
        @media (max-width: 768px) {
            .dashboard {
                grid-template-columns: 1fr;
            }
            
            header {
                flex-direction: column;
                gap: 10px;
            }
            
            .controls {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-balance-scale"></i>
                <span>Court Case Management System</span>
            </div>
            <div class="controls">
                <button class="btn btn-warning" id="updateCourtBtn">
                    <i class="fas fa-edit"></i> Update Court Name
                </button>
                <button class="btn btn-primary" id="refreshBtn">
                    <i class="fas fa-sync-alt"></i> Refresh
                </button>
                <button class="btn btn-success" id="saveBtn">
                    <i class="fas fa-save"></i> Local Save
                </button>
            </div>
        </header>

        <div class="court-info">
            <div class="court-name" id="courtName">In the Court of District and Sessions Judge, Battagram</div>
            <div class="date-display">
                <span id="currentDate">1-Aug to 23-Aug-25</span>
                <span id="currentTime">12:50:59 PM</span>
            </div>
            
            <div class="dashboard">
                <div class="data-table">
                    <h2>Case Management</h2>
                    <table>
                        <thead>
                            <tr>
                                <th>Types</th>
                                <th>Criminal</th>
                                <th>Civil</th>
                                <th>Total</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Previous Month (July) Pendency</td>
                                <td><input type="number" id="prevCriminal" value="10"></td>
                                <td><input type="number" id="prevCivil" value="10"></td>
                                <td id="prevTotal">20</td>
                            </tr>
                            <tr>
                                <td>INSTITUTION CASES</td>
                                <td><input type="number" id="instCriminal" value="10"></td>
                                <td><input type="number" id="instCivil" value="10"></td>
                                <td id="instTotal">20</td>
                            </tr>
                            <tr>
                                <td>
                                    DISPOSED CASES
                                    <div class="case-note">Do not add Transfer Out Cases here</div>
                                </td>
                                <td><input type="number" id="dispCriminal" value="10"></td>
                                <td><input type="number" id="dispCivil" value="10"></td>
                                <td id="dispTotal">20</td>
                            </tr>
                            <tr>
                                <td>
                                    Transfer In Cases
                                    <div class="case-note">Not effect institution % but effect (+) in Pendency only</div>
                                </td>
                                <td><input type="number" id="inCriminal" value="10"></td>
                                <td><input type="number" id="inCivil" value="10"></td>
                                <td id="inTotal">20</td>
                            </tr>
                            <tr>
                                <td>
                                    Transfer Out Cases
                                    <div class="case-note">Not effect Disposed % but effect (-) Pendency only</div>
                                </td>
                                <td><input type="number" id="outCriminal" value="10"></td>
                                <td><input type="number" id="outCivil" value="10"></td>
                                <td id="outTotal">20</td>
                            </tr>
                            <tr>
                                <td>Percentage</td>
                                <td id="percentCriminal" class="percentage-bold">100.00%</td>
                                <td id="percentCivil" class="percentage-bold">100.00%</td>
                                <td id="percentTotal" class="percentage-bold">100.00%</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <div class="summary">
                    <h2>Summary</h2>
                    <div class="summary-item">
                        <span>Target</span>
                        <span>110%</span>
                    </div>
                    <div class="target-message" id="targetMessage">
                        At this stage, if the given number of pending cases are disposed of,
                        this Court will achieve 110% of its disposal target.
                    </div>
                    <div class="summary-item">
                        <span>Total Current Pendency</span>
                        <span id="totalPendency">20</span>
                    </div>
                    <div class="summary-item">
                        <span>Criminal Pendency</span>
                        <span id="criminalPendency">10</span>
                    </div>
                    <div class="summary-item">
                        <span>Civil Pendency</span>
                        <span id="civilPendency">10</span>
                    </div>
                    <div class="summary-item">
                        <span>Target Need Cases</span>
                        <span id="additionalCases">0</span>
                    </div>
                </div>
            </div>
            
            <button class="btn btn-success" id="generateReport" style="width: 100%; margin-top: 20px;">
                <i class="fas fa-file-pdf"></i> Generate Report
            </button>
        </div>

        <div class="report" id="reportSection">
            <div class="report-header">
                <h1 id="reportCourtName">In the Court of District and Sessions Judge, Battagram</h1>
                <p><strong>Percentage Target & Pendency</strong></p>
                <p id="reportDate">Saturday, August 23, 2025</p>
            </div>
            
            <div class="report-table">
                <h3>Current Percentage</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Type</th>
                            <th>Institution Cases</th>
                            <th>Disposed Cases</th>
                            <th>Percentage</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>Criminal Cases</strong></td>
                            <td id="repInstCriminal">10</td>
                            <td id="repDispCriminal">10</td>
                            <td id="repPercentCriminal" class="report-bold">100.00%</td>
                        </tr>
                        <tr>
                            <td><strong>Civil Cases</strong></td>
                            <td id="repInstCivil">10</td>
                            <td id="repDispCivil">10</td>
                            <td id="repPercentCivil" class="report-bold">100.00%</td>
                        </tr>
                        <tr>
                            <td class="report-bold">Total Cases</td>
                            <td id="repInstTotal" class="report-bold">20</td>
                            <td id="repDispTotal" class="report-bold">20</td>
                            <td id="repPercentTotal" class="report-bold">100.00%</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div class="target-message" id="repTargetMessage">
                At this stage, if the given number of pending cases are disposed of, this Court will achieve 110% of its disposal target.
            </div>
            
            <div class="report-table">
                <h3>Current total Pendency till now</h3>
                <table>
                    <thead>
                        <tr>
                            <th>Type</th>
                            <th>Criminal</th>
                            <th>Civil</th>
                            <th>Total</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Current Month Cases</td>
                            <td id="repCurCriminal">10</td>
                            <td id="repCurCivil">10</td>
                            <td id="repCurTotal">20</td>
                        </tr>
                        <tr>
                            <td>Transfer in Cases</td>
                            <td id="repInCriminal">10</td>
                            <td id="repInCivil">10</td>
                            <td id="repInTotal">20</td>
                        </tr>
                        <tr>
                            <td>Transfer Out Cases</td>
                            <td id="repOutCriminal">10</td>
                            <td id="repOutCivil">10</td>
                            <td id="repOutTotal">20</td>
                        </tr>
                        <tr>
                            <td class="report-bold">Total Pendency</td>
                            <td id="repTotalCriminal" class="report-bold">20</td>
                            <td id="repTotalCivil" class="report-bold">20</td>
                            <td id="repGrandTotal" class="report-bold">40</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            
            <div class="signature">
                <div class="signature-line">
                    <p>SIGNATURE</p>
                </div>
                <p>Reader/Muharrir</p>
            </div>
            
            <div class="action-buttons no-print">
                <button class="btn btn-danger" onclick="window.print()">
                    <i class="fas fa-download"></i> Download PDF
                </button>
                <button class="btn btn-primary" id="backBtn">
                    <i class="fas fa-arrow-left"></i> Back to Entries
                </button>
            </div>
        </div>
    </div>

    <div class="edit-court-modal" id="courtModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Update Court Name</h2>
                <button class="close-modal" id="closeModal">&times;</button>
            </div>
            <input type="text" class="court-name-input" id="courtNameInput" placeholder="Enter court name">
            <div class="modal-actions">
                <button class="btn btn-primary" id="saveCourtName">Save Changes</button>
                <button class="btn btn-danger" id="cancelCourtName">Cancel</button>
            </div>
        </div>
    </div>

    <div class="save-notification" id="saveNotification">
        <i class="fas fa-check-circle"></i> Data saved successfully!
    </div>

    <script>
        // Format date as "1-Aug", "2-Aug", etc.
        function formatDate(date) {
            const day = date.getDate();
            const month = date.toLocaleString('default', { month: 'short' });
            return `${day}-${month}`;
        }
        
        // Format date for report header
        function formatReportDate(date) {
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            return date.toLocaleDateString('en-US', options);
        }
        
        // Update current date and time
        function updateDateTime() {
            const now = new Date();
            
            // Get first day of current month
            const firstDay = new Date(now.getFullYear(), now.getMonth(), 1);
            
            // Format date range (1-Aug to CurrentDate)
            const dateRange = `${formatDate(firstDay)} to ${formatDate(now)}-${now.getFullYear().toString().slice(-2)}`;
            document.getElementById('currentDate').textContent = dateRange;
            
            // Update time
            const timeString = now.toLocaleTimeString('en-US', { 
                hour: '2-digit', 
                minute: '2-digit', 
                second: '2-digit',
                hour12: true 
            });
            document.getElementById('currentTime').textContent = timeString;
            
            // Update report date
            document.getElementById('reportDate').textContent = formatReportDate(now);
        }
        
        // Initial date/time update and set interval
        updateDateTime();
        setInterval(updateDateTime, 1000);
        
        // Save all data to localStorage
        function saveDataToLocalStorage() {
            const data = {
                courtName: document.getElementById('courtName').textContent,
                prevCriminal: document.getElementById('prevCriminal').value,
                prevCivil: document.getElementById('prevCivil').value,
                instCriminal: document.getElementById('instCriminal').value,
                instCivil: document.getElementById('instCivil').value,
                dispCriminal: document.getElementById('dispCriminal').value,
                dispCivil: document.getElementById('dispCivil').value,
                inCriminal: document.getElementById('inCriminal').value,
                inCivil: document.getElementById('inCivil').value,
                outCriminal: document.getElementById('outCriminal').value,
                outCivil: document.getElementById('outCivil').value
            };
            
            localStorage.setItem('courtCaseData', JSON.stringify(data));
            
            // Show save notification
            const notification = document.getElementById('saveNotification');
            notification.style.display = 'block';
            setTimeout(() => {
                notification.style.display = 'none';
            }, 3000);
        }
        
        // Load data from localStorage
        function loadDataFromLocalStorage() {
            const savedData = localStorage.getItem('courtCaseData');
            if (savedData) {
                const data = JSON.parse(savedData);
                
                document.getElementById('courtName').textContent = data.courtName;
                document.getElementById('prevCriminal').value = data.prevCriminal;
                document.getElementById('prevCivil').value = data.prevCivil;
                document.getElementById('instCriminal').value = data.instCriminal;
                document.getElementById('instCivil').value = data.instCivil;
                document.getElementById('dispCriminal').value = data.dispCriminal;
                document.getElementById('dispCivil').value = data.dispCivil;
                document.getElementById('inCriminal').value = data.inCriminal;
                document.getElementById('inCivil').value = data.inCivil;
                document.getElementById('outCriminal').value = data.outCriminal;
                document.getElementById('outCivil').value = data.outCivil;
                
                calculateTotals();
            }
        }
        
        // Calculate totals and percentages
        function calculateTotals() {
            // Get input values
            const prevCriminal = parseInt(document.getElementById('prevCriminal').value) || 0;
            const prevCivil = parseInt(document.getElementById('prevCivil').value) || 0;
            const instCriminal = parseInt(document.getElementById('instCriminal').value) || 0;
            const instCivil = parseInt(document.getElementById('instCivil').value) || 0;
            const dispCriminal = parseInt(document.getElementById('dispCriminal').value) || 0;
            const dispCivil = parseInt(document.getElementById('dispCivil').value) || 0;
            const inCriminal = parseInt(document.getElementById('inCriminal').value) || 0;
            const inCivil = parseInt(document.getElementById('inCivil').value) || 0;
            const outCriminal = parseInt(document.getElementById('outCriminal').value) || 0;
            const outCivil = parseInt(document.getElementById('outCivil').value) || 0;
            
            // Calculate totals
            document.getElementById('prevTotal').textContent = prevCriminal + prevCivil;
            document.getElementById('instTotal').textContent = instCriminal + instCivil;
            document.getElementById('dispTotal').textContent = dispCriminal + dispCivil;
            document.getElementById('inTotal').textContent = inCriminal + inCivil;
            document.getElementById('outTotal').textContent = outCriminal + outCivil;
            
            // Calculate percentages
            const percentCriminal = instCriminal > 0 ? (dispCriminal / instCriminal * 100).toFixed(2) : "0.00";
            const percentCivil = instCivil > 0 ? (dispCivil / instCivil * 100).toFixed(2) : "0.00";
            const percentTotal = (instCriminal + instCivil) > 0 ? 
                ((dispCriminal + dispCivil) / (instCriminal + instCivil) * 100).toFixed(2) : "0.00";
            
            document.getElementById('percentCriminal').textContent = percentCriminal + "%";
            document.getElementById('percentCivil').textContent = percentCivil + "%";
            document.getElementById('percentTotal').textContent = percentTotal + "%";
            
            // Calculate pendency using the formula: (Previous Month Pendency + Institution Cases + Transfer In) - (Disposed Cases + Transfer Out)
            const criminalPendency = prevCriminal + instCriminal + inCriminal - dispCriminal - outCriminal;
            const civilPendency = prevCivil + instCivil + inCivil - dispCivil - outCivil;
            const totalPendency = criminalPendency + civilPendency;
            
            document.getElementById('criminalPendency').textContent = criminalPendency;
            document.getElementById('civilPendency').textContent = civilPendency;
            document.getElementById('totalPendency').textContent = totalPendency;
            
            // Calculate additional cases needed using the formula: =IF(D7>=110%, "Achieved", MAX(0, ROUNDUP(B7*1.1, 0) - C7))
            const totalInstitution = instCriminal + instCivil;
            const totalDisposed = dispCriminal + dispCivil;
            const disposalPercentage = totalInstitution > 0 ? (totalDisposed / totalInstitution * 100) : 0;
            
            let additionalCasesNeeded = 0;
            let targetMessage = "At this stage, if the given number of pending cases are disposed of, this Court will achieve 110% of its disposal target.";
            
            if (disposalPercentage >= 110) {
                additionalCasesNeeded = "Achieved";
                targetMessage = "<strong>This Court has already achieved 110% of its disposal target!</strong>";
            } else {
                additionalCasesNeeded = Math.max(0, Math.ceil(totalInstitution * 1.1) - totalDisposed);
                targetMessage = `At this stage, if <strong>${additionalCasesNeeded}</strong> more cases are disposed of, this Court will achieve 110% of its disposal target.`;
            }
            
            document.getElementById('additionalCases').textContent = additionalCasesNeeded;
            document.getElementById('targetMessage').innerHTML = targetMessage;
            if (disposalPercentage >= 110) {
                document.getElementById('targetMessage').innerHTML += ' <span class="achieved-badge">Target Achieved!</span>';
            }
        }
        
        // Set up event listeners for input changes
        const inputs = document.querySelectorAll('input[type="number"]');
        inputs.forEach(input => {
            input.addEventListener('input', calculateTotals);
        });
        
        // Load saved data when page loads
        window.addEventListener('DOMContentLoaded', (event) => {
            loadDataFromLocalStorage();
        });
        
        // Initial calculation
        calculateTotals();
        
        // Generate report
        document.getElementById('generateReport').addEventListener('click', function() {
            // Get input values
            const prevCriminal = parseInt(document.getElementById('prevCriminal').value) || 0;
            const prevCivil = parseInt(document.getElementById('prevCivil').value) || 0;
            const instCriminal = parseInt(document.getElementById('instCriminal').value) || 0;
            const instCivil = parseInt(document.getElementById('instCivil').value) || 0;
            const dispCriminal = parseInt(document.getElementById('dispCriminal').value) || 0;
            const dispCivil = parseInt(document.getElementById('dispCivil').value) || 0;
            const inCriminal = parseInt(document.getElementById('inCriminal').value) || 0;
            inCivil = parseInt(document.getElementById('inCivil').value) || 0;
            const outCriminal = parseInt(document.getElementById('outCriminal').value) || 0;
            const outCivil = parseInt(document.getElementById('outCivil').value) || 0;
            
            // Update report values
            document.getElementById('repInstCriminal').textContent = instCriminal;
            document.getElementById('repInstCivil').textContent = instCivil;
            document.getElementById('repInstTotal').textContent = instCriminal + instCivil;
            
            document.getElementById('repDispCriminal').textContent = dispCriminal;
            document.getElementById('repDispCivil').textContent = dispCivil;
            document.getElementById('repDispTotal').textContent = dispCriminal + dispCivil;
            
            document.getElementById('repPercentCriminal').textContent = document.getElementById('percentCriminal').textContent;
            document.getElementById('repPercentCivil').textContent = document.getElementById('percentCivil').textContent;
            document.getElementById('repPercentTotal').textContent = document.getElementById('percentTotal').textContent;
            
            // Calculate Current Month Cases using formula: Previous Month Cases + Institution Cases - Disposed Cases
            const currentMonthCriminal = prevCriminal + instCriminal - dispCriminal;
            const currentMonthCivil = prevCivil + instCivil - dispCivil;
            
            document.getElementById('repCurCriminal').textContent = currentMonthCriminal;
            document.getElementById('repCurCivil').textContent = currentMonthCivil;
            document.getElementById('repCurTotal').textContent = currentMonthCriminal + currentMonthCivil;
            
            document.getElementById('repInCriminal').textContent = inCriminal;
            document.getElementById('repInCivil').textContent = inCivil;
            document.getElementById('repInTotal').textContent = inCriminal + inCivil;
            
            document.getElementById('repOutCriminal').textContent = outCriminal;
            document.getElementById('repOutCivil').textContent = outCivil;
            document.getElementById('repOutTotal').textContent = outCriminal + outCivil;
            
            // Calculate Total Pendency using formula: Previous Month Cases + Institution Cases - Disposed Cases + Transfer In Cases - Transfer Out Cases
            const totalPendencyCriminal = prevCriminal + instCriminal - dispCriminal + inCriminal - outCriminal;
            const totalPendencyCivil = prevCivil + instCivil - dispCivil + inCivil - outCivil;
            
            document.getElementById('repTotalCriminal').textContent = totalPendencyCriminal;
            document.getElementById('repTotalCivil').textContent = totalPendencyCivil;
            document.getElementById('repGrandTotal').textContent = totalPendencyCriminal + totalPendencyCivil;
            
            // Update court name in report
            document.getElementById('reportCourtName').textContent = document.getElementById('courtName').textContent;
            
            // Update target message in report
            document.getElementById('repTargetMessage').innerHTML = document.getElementById('targetMessage').innerHTML;
            
            // Show report section
            document.getElementById('reportSection').style.display = 'block';
            
            // Scroll to report
            document.getElementById('reportSection').scrollIntoView({ behavior: 'smooth' });
        });
        
        // Back to entries button
        document.getElementById('backBtn').addEventListener('click', function() {
            document.getElementById('reportSection').style.display = 'none';
        });
        
        // Refresh button
        document.getElementById('refreshBtn').addEventListener('click', function() {
            if (confirm('Are you sure you want to refresh all data? This will reset all values.')) {
                inputs.forEach(input => {
                    input.value = '0';
                });
                calculateTotals();
                // Clear saved data
                localStorage.removeItem('courtCaseData');
            }
        });
        
        // Save button - save data to localStorage
        document.getElementById('saveBtn').addEventListener('click', function() {
            saveDataToLocalStorage();
        });
        
        // Court name editing functionality
        const courtModal = document.getElementById('courtModal');
        const courtNameInput = document.getElementById('courtNameInput');
        const courtNameElement = document.getElementById('courtName');
        const updateCourtBtn = document.getElementById('updateCourtBtn');
        const closeModal = document.getElementById('closeModal');
        const cancelCourtName = document.getElementById('cancelCourtName');
        const saveCourtName = document.getElementById('saveCourtName');
        
        // Open modal
        updateCourtBtn.addEventListener('click', function() {
            courtNameInput.value = courtNameElement.textContent;
            courtModal.style.display = 'flex';
        });
        
        // Close modal
        function closeCourtModal() {
            courtModal.style.display = 'none';
        }
        
        closeModal.addEventListener('click', closeCourtModal);
        cancelCourtName.addEventListener('click', closeCourtModal);
        
        // Save court name
        saveCourtName.addEventListener('click', function() {
            const newCourtName = courtNameInput.value.trim();
            if (newCourtName) {
                courtNameElement.textContent = newCourtName;
                closeCourtModal();
                // Save the updated court name
                saveDataToLocalStorage();
            } else {
                alert('Court name cannot be empty!');
            }
        });
        
        // Close modal if clicked outside
        window.addEventListener('click', function(event) {
            if (event.target === courtModal) {
                closeCourtModal();
            }
        });
        
        // Auto-save when inputs change (optional)
        inputs.forEach(input => {
            input.addEventListener('change', saveDataToLocalStorage);
        });
    </script>
</body>
</html>
