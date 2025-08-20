---
layout: splash
title: ADC Survey
permalink: /adc_survey/
---

<style>
.survey-container {
    display: flex;
    align-items: flex-start;
    gap: 2em;
    margin: 2em 0;
}

.image-section {
    flex: 1;
    max-width: 50%;
}

.input-section {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 0.75em;
    padding-left: 2em;
    max-width: 40%;
}

.input-field {
    padding: 0.8em;
    font-size: 1em;
    border: 2px solid #ccc;
    border-radius: 5px;
    width: 50%;
    box-sizing: border-box;
    margin-left: auto;
}

.input-field:focus {
    outline: none;
    border-color: #007acc;
}

.input-group {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 1em;
    justify-content: space-between;
}

.input-label {
    font-weight: bold;
    font-size: 1em;
    color: #333;
    margin-bottom: 0;
    min-width: 120px;
    text-align: left;
    flex-shrink: 0;
}

.evaluation-field {
    padding: 0.8em;
    font-size: 1em;
    border: 2px solid #28a745;
    border-radius: 5px;
    width: 100%;
    box-sizing: border-box;
    background-color: #f8f9fa;
    font-weight: bold;
    color: #28a745;
    text-align: center;
    margin-top: 0.25em;
    margin-bottom: 0.25em;
}

.calc-selection {
    display: flex;
    flex-direction: row;
    gap: 1em;
    align-items: baseline;
    justify-content: space-between;
    margin-bottom: 1em;
    padding: 0.8em 1.5em;
    border: 1px solid #ddd;
    border-radius: 5px;
    background-color: #f9f9f9;
    width: 100%;
    box-sizing: border-box;
}

.calc-dropdown {
    padding: 0.6em 1em;
    font-size: 1em;
    border: 2px solid #ccc;
    border-radius: 5px;
    background-color: white;
    cursor: pointer;
    min-width: 200px;
    margin: 0;
    vertical-align: baseline;
}

.calc-dropdown:focus {
    outline: none;
    border-color: #007acc;
}

.fom-slider-container {
    display: flex;
    flex-direction: row;
    gap: 1em;
    align-items: baseline;
    margin: 0;
    margin-left: auto;
}

.fom-slider-label {
    font-weight: bold;
    font-size: 1em;
    color: #333;
    margin: 0;
    white-space: nowrap;
}

.fom-slider {
    width: 150px;
    height: 6px;
    border-radius: 3px;
    background: #ddd;
    outline: none;
    -webkit-appearance: none;
    appearance: none;
    cursor: pointer;
}

.fom-slider::-webkit-slider-thumb {
    appearance: none;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: #007acc;
    cursor: pointer;
    border: 2px solid #fff;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.fom-slider::-moz-range-thumb {
    width: 18px;
    height: 18px;
    border-radius: 50%;
    background: #007acc;
    cursor: pointer;
    border: 2px solid #fff;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.fom-value-display {
    font-size: 0.9em;
    color: #666;
    margin: 0;
    min-width: 80px;
    width: 80px;
    text-align: center;
}
</style>

## ADC Performance Survey Envelope Calculator

<!-- Calculation Mode Selection - spans full width -->
<div class="calc-selection">
    <h4 style="margin: 0; vertical-align: baseline;">Select parameter to calculate:</h4>
    <select id="calcMode" class="calc-dropdown" onchange="updateCalculation()">
        <option value="power">Power</option>
        <option value="sndr">SNDR</option>
        <option value="fs">FsNyq</option>
    </select>
    
    <div class="fom-slider-container">
        <label class="fom-slider-label">FOM Adjustment:</label>
        <input type="range" id="fomSlider" class="fom-slider" min="-6" max="0" step="0.5" value="-3" oninput="updateFomDisplay(); updateCalculation()">
        <span id="fomValue" class="fom-value-display">-3.0 dB</span>
    </div>
</div>

<div class="survey-container">
    <div class="image-section">
        <!-- Image with clickable link -->
        <a href="https://raw.githubusercontent.com/bmurmann/ADC-survey/refs/heads/main/plots/foms_plot.png" target="_blank">
            <img src="https://raw.githubusercontent.com/bmurmann/ADC-survey/refs/heads/main/plots/foms_plot.png" alt="ADC Performance Survey Chart" style="max-width: 100%; height: auto; border-radius: 5px;">
        </a>
        <p>
            <a href="https://github.com/bmurmann/ADC-survey" target="_blank" style="text-decoration: none; color: #000000ff; display: inline-flex; align-items: center; gap: 0.5em;">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor" style="vertical-align: middle;">
                    <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/>
                </svg>
                <em>ADC survey on GitHub</em>
            </a>
        </p>
    </div>
    
    <div class="input-section">
        <!-- Input fields will be dynamically updated based on calculation mode -->
        <div class="input-group" id="inputGroup1">
            <label class="input-label" id="label1">SNDR (dB):</label>
            <input type="text" class="input-field" id="input1" placeholder="Enter values" value="Enter values" oninput="updateCalculation()">
        </div>
        
        <div class="input-group" id="inputGroup2">
            <label class="input-label" id="label2">FsNyq (Hz):</label>
            <input type="text" class="input-field" id="input2" placeholder="Enter values" value="Enter values" oninput="updateCalculation()">
        </div>
        
        <div class="input-group" id="inputGroup3" style="display: none;">
            <label class="input-label" id="label3">Power (W):</label>
            <input type="text" class="input-field" id="input3" placeholder="Enter values" value="Enter values" oninput="updateCalculation()">
        </div>
        
        <div class="evaluation-field" id="resultField1">Power: Not calculated</div>
        
        <div class="evaluation-field" id="resultField2" style="border-color: #007bff; color: #007bff;">FOMS: Not calculated</div>
    </div>
</div>

<script>
// Variable to store the JSON data as key-value pairs
let fomsData = {};

// Function to format numbers in engineering notation with units
function formatEngineering(num, unit = '') {
    if (num === 0) return "0" + unit;
    
    const absNum = Math.abs(num);
    const sign = num < 0 ? "-" : "";
    
    // Define the engineering prefixes
    const prefixes = [
        { value: 1e12, symbol: 'T' },
        { value: 1e9, symbol: 'G' },
        { value: 1e6, symbol: 'M' },
        { value: 1e3, symbol: 'k' },
        { value: 1, symbol: '' },
        { value: 1e-3, symbol: 'm' },
        { value: 1e-6, symbol: 'µ' },
        { value: 1e-9, symbol: 'n' },
        { value: 1e-12, symbol: 'p' },
        { value: 1e-15, symbol: 'f' }
    ];
    
    // Find the appropriate prefix
    for (let prefix of prefixes) {
        if (absNum >= prefix.value) {
            const scaledValue = absNum / prefix.value;
            const digits = scaledValue >= 100 ? 0 : scaledValue >= 10 ? 1 : 2;
            return sign + scaledValue.toFixed(digits) + ' ' + prefix.symbol + unit;
        }
    }
    
    // For very small numbers, use scientific notation
    return num.toExponential(2) + unit;
}

// Function to fetch JSON data from GitHub
async function fetchFomsData() {
    try {
        const response = await fetch('https://raw.githubusercontent.com/bmurmann/ADC-survey/main/plots/foms_plot.json');
        if (response.ok) {
            const jsonData = await response.json();
            fomsData = jsonData;
            console.log('FoMs JSON data loaded:', fomsData);
        } else {
            console.error('Failed to fetch FoMs data:', response.status);
            displayErrorMessage();
        }
    } catch (error) {
        console.error('Error fetching FoMs data:', error);
        displayErrorMessage();
    }
}

// Function to display error message
function displayErrorMessage() {
    const jsonDisplay = document.getElementById('jsonDisplay');
    if (jsonDisplay) {
        jsonDisplay.textContent = 'Failed to load FoMs JSON data. Please check your internet connection.';
        jsonDisplay.style.color = '#d32f2f';
    }
}

// Fetch JSON data when page loads
document.addEventListener('DOMContentLoaded', function() {
    fetchFomsData();
    
    // Initialize the interface for the default mode
    updateInterface();
    
    // Initialize FOM slider display
    updateFomDisplay();
    
    // Your existing input field logic
    const inputs = document.querySelectorAll('.input-field');
    inputs.forEach(input => {
        input.addEventListener('focus', function() {
            if (this.value === 'Enter values') {
                this.value = '';
            }
        });
        
        input.addEventListener('blur', function() {
            if (this.value === '') {
                this.value = 'Enter values';
                updateCalculation();
            }
        });
    });
});

function updateFomDisplay() {
    const slider = document.getElementById('fomSlider');
    const display = document.getElementById('fomValue');
    const value = parseFloat(slider.value);
    display.textContent = `${value.toFixed(1)} dB`;
}

function updateInterface() {
    const modes = {
        power: { groups: [1,2], labels: ['SNDR (dB):', 'FsNyq (Hz):'], result: 'Power' },
        sndr: { groups: [2,3], labels: [,'FsNyq (Hz):', 'Power (W):'], result: 'SNDR' },
        fs: { groups: [1,3], labels: ['SNDR (dB):',, 'Power (W):'], result: 'FsNyq' }
    };
    
    const mode = modes[document.getElementById('calcMode').value];
    [1,2,3].forEach(i => document.getElementById(`inputGroup${i}`).style.display = 'none');
    mode.groups.forEach(i => {
        document.getElementById(`inputGroup${i}`).style.display = 'flex';
        if(mode.labels[i-1]) document.getElementById(`label${i}`).textContent = mode.labels[i-1];
    });
    document.getElementById('resultField1').textContent = `${mode.result}: Not calculated`;
    document.getElementById('resultField2').textContent = 'FOMS: Not calculated';
}

function updateCalculation() {
    updateInterface();
    
    const getVal = (id) => {
        const val = document.getElementById(id).value;
        return isNaN(parseFloat(val)) || val === "Enter values" ? 0 : parseFloat(val);
    };
    
    const setResult = (text1, text2) => {
        document.getElementById('resultField1').textContent = text1;
        document.getElementById('resultField2').textContent = text2;
    };
    
    const mode = document.getElementById('calcMode').value;
    const [sndr, fsNyq, power] = [getVal('input1'), getVal('input2'), getVal('input3')];
    const fomAdjustment = parseFloat(document.getElementById('fomSlider').value);
    
    if (!isFomsDataReady()) return setResult(`${mode === 'power' ? 'Power' : mode === 'sndr' ? 'SNDR' : 'FsNyq'}: Waiting for data...`, 'FOMS: Waiting for data...');
    
    const { f_corner: fCorner, foms_db_asymp: fomsDbAsymp } = fomsData;
    
    if (mode === 'power') {
        if (!areInputsValid(sndr, fsNyq)) return setResult('Power: Invalid inputs (SNDR and FsNyq must be > 0)', 'FOMS: Invalid inputs');
        const foms = calculateFOMS(fsNyq, fCorner, fomsDbAsymp, fomAdjustment);
        const result = fsNyq / 2 / Math.pow(10, (foms - sndr) / 10);
        setResult(`Power: ${formatEngineering(result, 'W')}`, `FOMS: ${foms.toFixed(2)} dB`);
        document.getElementById('input3').value = result.toString();
    } else if (mode === 'sndr') {
        if (fsNyq <= 0 || power <= 0) return setResult('SNDR: Invalid inputs (FsNyq and Power must be > 0)', 'FOMS: Invalid inputs');
        const foms = calculateFOMS(fsNyq, fCorner, fomsDbAsymp, fomAdjustment);
        const result = foms - 10 * Math.log10(fsNyq / 2 / power);
        setResult(`SNDR: ${result.toFixed(2)} dB`, `FOMS: ${foms.toFixed(2)} dB`);
        document.getElementById('input1').value = result.toString();
    } else { // fs mode
        if (!areInputsValid(sndr, 1, power)) return setResult('FsNyq: Invalid inputs (SNDR and Power must be > 0)', 'FOMS: Invalid inputs');
        let result = 2 * power * Math.pow(10, (fomsDbAsymp - sndr) / 10);
        for (let i = 0; i < 20; i++) {
            const f = calculateFOMS(result, fCorner, fomsDbAsymp, fomAdjustment) - sndr - 10 * Math.log10(result / 2 / power);
            const df = -10 / Math.LN10 * result / (Math.pow(fCorner, 2) + Math.pow(result, 2)) - 10 / Math.LN10 / result;
            if (Math.abs(f) < 1e-12 || Math.abs(df) < 1e-15) break;
            const newResult = result - f / df;
            result = newResult > 0 ? newResult : result / 2;
        }
        const foms = calculateFOMS(result, fCorner, fomsDbAsymp, fomAdjustment);
        setResult(`FsNyq: ${formatEngineering(result, 'Hz')}`, `FOMS: ${foms.toFixed(2)} dB`);
        document.getElementById('input2').value = result.toString();
    }
}

// Helper functions
const calculateFOMS = (fsNyq, fCorner, fomsDbAsymp, fomAdjustment = 0) => fomsDbAsymp - 10 * Math.log10(Math.pow(1 + Math.pow(fsNyq / fCorner, 2), 1/2)) + fomAdjustment;
const areInputsValid = (sndr, fsNyquist, power = null) => sndr > 0 && fsNyquist > 0 && (power === null || power > 0);
const isFomsDataReady = () => Object.keys(fomsData).length > 0 && fomsData["foms_db_asymp"] && fomsData["f_corner"];
</script>