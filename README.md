# GCD-γ Analyzer
Current version: 1.0

A web app to analyze galvanostatic charge-discharge (GCD) curves of electrochemical energy storage devices. From a discharge
curve it computes the gamma (γ) deviation coefficient, the real and ideal
energy, and the power. It also plots the energy  and a Ragone curves,
and it is possible to download the figures and a results table as PDF.
Note: the tool integrates the voltage curve as provided, so the initial IR drop is included in the result. To exclude it, trim the input data to start after the drop.

The method behind the tool comes from Da Silva et al., Dissipative effects in nonideal supercapacitors and batteries, Journal of Energy Storage 69 (2023) 107985.


The tool runs online as a web application (no installation needed): https://gcdgammaanalyzer-pcpptkoup4uetneztas69p.streamlit.app/ . The instructions below are for running it locally.
needed:

\-Python 3.9 or newer

\-The packages listed in "requirements.txt"


# Installation instructions

git clone https://github.com/energysystemslab/GCD_Gamma_Analyzer.git
cd GCD_Gamma_Analyzer
pip install -r requirements.txt


# Run instructions

streamlit run GCD_Gamma_Analyzer.py

The app opens in the  browser.

#  Tutorial

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


Sample files are in the "examples/" folder. Each example includes the input file and the expected output (γ, energies, power). Upload the input file, set the parameters below, and check that the tool reproduces the expected values.:

* "Niobium\_pentoxide\_GCDs\_1V\_1dot25\_A\_per\_g\_current\_app\_0dot0005A\_0.0004g.csv" — the pseudocapacitor case from the paper.
* "Dados de Descarga RFB 04 modulos Fe-Fe\_0.001A\_400ml\_each\_pole.csv" — the iron redox flow battery case.

Pseudocapacitor: device = Supercapacitor, current = 0.0005 A, active mass = 0.0004 g → expected γ = 0.84.
Redox flow battery: device = Battery, volume basis, 400 mL/pole, current = 0.001 A → expected γ = 0.7854.

# License

This project is released under the MIT License. See  file named
"LICENSE".

Contact:
Eric Pereira — expereira@shockers.wichita.edu

