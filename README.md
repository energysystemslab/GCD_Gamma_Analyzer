# GCD-γ Analyzer


A web app to analyze galvanostatic charge-discharge (GCD) curves.
It works for supercapacitors and battery-type devices. From a discharge
curve it computes the gamma (γ) deviation coefficient, the real and ideal
energy, and the power. It also draws the energy plot and a Ragone plot,
and it is possible to download the figures and a results table as PDF.

The method behind the tool:

needed:

\-Python 3.9 or newer

\-The packages listed in "requirements.txt"


# Install

git clone https://github.com/energysystemslab/GCD_Gamma_Analyzer.git
cd GCD_Gamma_Analyzer
pip install -r requirements.txt


# Run

streamlit run gcd\_analyzer.py

The app opens in the  browser.

# How to use

1. Upload a CSV or Excel file with your discharge data.
2. Type the name of the time column and the voltage column.
3. Set the applied current, the active mass (or electrolyte volume for
flow batteries), and the device type.
4. Click **Run analysis**.

The app wil calculates gamma, the real and ideal energy, the corrected energy, and
the power. It is possible to download the plots and the results table as PDF, or the
table as CSV.

# Input file format

The file needs at least two columns: one for time (in seconds) and one for
voltage (in volts). Column names are set in the app, so they can match your
equipment output.

Example:

|Elapsed Time (s)|Voltage(V)|
|-|-|
|0.0|1.80|
|0.5|1.79|
|...|...|

## Example data

Sample files are in the "examples/" folder:

* "Niobium\_pentoxide\_GCDs\_1V\_1dot25\_A\_per\_g\_current\_app\_0dot0005A\_0.0004g.csv" — the pseudocapacitor case from the paper.
* "Dados de Descarga RFB 04 modulos Fe-Fe\_0.001A\_400ml\_each\_pole.csv" — the iron redox flow battery case.

# License

This project is released under the MIT License. See  file named
"LICENSE".

# Contact
Eric Pereira — expereira@shockers.wichita.edu

