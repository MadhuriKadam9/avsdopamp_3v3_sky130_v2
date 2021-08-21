# Cmosopamp
CMOS OPAMP is Basic building block of analog and Mixe signal circuits. It is used in many applications such as ADC, DAC and Instrumentation Amplifier.
It basically amplifies the difference between two input signals.
# Instumentation Amplifier: An Application Of CMOS OPAMP
<img width="661" alt="Instru-Amp" src="https://user-images.githubusercontent.com/88900482/130283601-f840c5fe-f285-4f46-92b2-f93b9e5e9480.PNG">

# Performance parameters of Bandgap Reference IP
<img width="515" alt="Perfor-para" src="https://user-images.githubusercontent.com/88900482/130284019-6360918c-f9c1-4a17-8416-c410cce3271c.PNG">

# Block Diagram of CMOS OPAMP IP
<img width="345" alt="OPAMP-Block Dig" src="https://user-images.githubusercontent.com/88900482/130284202-28dce16c-5f7b-45a7-916d-11d1ce77082a.PNG">

# Downloading the files on your System
The files from this repository can be downloaded and used by the following commands :-

sudo apt install -y git

git clone https://github.com/MadhuriKadam9/Cmosopamp.git


# Pre-Layout Simulation of CMOS OPAMP IP 
## 1. Schematic of CMOS OPAMP IP designd in eSim
Install the eSim tool using this https://esim.fossee.in/downloads  
Note: You can also refer to the eSim Spoken Tutorialwebsite https://spoken-tutorial.org/tutorial-search/?search_foss=eSim

<img width="573" alt="Combined_ckt" src="https://user-images.githubusercontent.com/88900482/130285141-6a033032-0108-4130-aff0-3394034cd5aa.png">

## 2. Ngspice Simulation Results
Ngspice is an open source mixed-signal circuit simulator. To install Ngspice on Ubuntu, open terminal window and type :-

sudo apt-get install -y ngspice

After successful installation, to invoke Ngspice type the following command on the terminal window.

ngspice "circuit file to be simulated"

### A) Transient Response of Two stage OPAMP
To get the transient response of two stage OPAMP run the following file in ngspice: Opamp_TRAN.cir.out

<img width="921" alt="Vin-tran" src="https://user-images.githubusercontent.com/88900482/130285858-8b30650b-a886-4e35-972b-5ece61a7e057.PNG">


<img width="945" alt="Vout-tran" src="https://user-images.githubusercontent.com/88900482/130286285-eb1cbb5c-641b-47d3-a2c8-aef8183c81c9.PNG">

### B) AC Response of Two stage OPAMP
To get the transient response of two stage OPAMP run the following file in ngspice: Opamp_AC.cir.out

Magnitude Response Vout-dB i.e. ADM 
<img width="937" alt="vout-ac-magres" src="https://user-images.githubusercontent.com/88900482/130286370-f3c78ccf-c60a-47b1-aaed-abaa6ee4a8da.PNG">

Phase Response Vout-Ph
<img width="930" alt="vout-ac-phres" src="https://user-images.githubusercontent.com/88900482/130286446-a1fc6d44-0ce5-4ee9-9e3a-4a0a2d990779.PNG">

Phase Margin Plot of Vout
<img width="930" alt="vout-ac-pm (2)" src="https://user-images.githubusercontent.com/88900482/130286501-edc307f8-15bb-4a09-b437-c6735b6a2be5.PNG">

# Layout with Magic Tool
## MAGIC Tool installation:
The Layout for the circuit was done using Magic Layout editor tool. To observe the layout, install magic using the following commands :-

sudo wget "http://opencircuitdesign.com/magic/archive/magic-8.3.122.tgz"

tar -xvzf magic-8.3.122.tgz

cd magic-8.3.122

sudo ./configure

sudo make

sudo make install


## Resistor
After successful installation, To open Resistor layout in magic type following in terminal window:-

cd Cmosopamp/OPAMP_Layout_Files/

magic -T ../libs/sky130A.tech res.mag


<img width="258" alt="Resistor" src="https://user-images.githubusercontent.com/88900482/130286663-1837abf3-2aca-4d53-a730-280819ec12bf.PNG">

## Capacitor
To see capacitor layout give command    magic -T ../libs/sky130A.tech mimcapt.mag

<img width="277" alt="Mimcap" src="https://user-images.githubusercontent.com/88900482/130286698-14e366b5-dc1c-45ad-94a3-79a59edd8f5d.PNG">


## Single stage OPAMP
To see opamp1 layout give command    magic -T ../libs/sky130A.tech opamp1.mag
<img width="553" alt="OPAMP1" src="https://user-images.githubusercontent.com/88900482/130286722-b432a8a2-be15-4cbd-bd4b-abca911322af.PNG">

## Dual Stage OPAMP
To see opamp2 layout give command    magic -T ../libs/sky130A.tech opamp2.mag
<img width="730" alt="Opamp2" src="https://user-images.githubusercontent.com/88900482/130286739-103c6a5f-bd6a-4d54-ab49-cc80a09e2f53.PNG">


# Post-Layout Simulation of CMOS OPAMP IP
## Single Stage OPAMP
### Transient Response
Run the following file in ngspice: opamp1_tran.spice

1) Vinp, Vinm Waveforms
<img width="868" alt="Vin-tran" src="https://user-images.githubusercontent.com/88900482/130287209-24711fbb-40fe-4797-a4ff-fcc74efb5505.PNG">

2) Vo waveform
<img width="875" alt="Vo-trans" src="https://user-images.githubusercontent.com/88900482/130287239-f1b2c2e3-7a19-42c9-8544-f86af1b419c6.PNG">

### AC Response
Run the following file in ngspice: opamp1_ac.spice

1) Magnitude Response i.e. VodB
<img width="878" alt="VOdb-AC" src="https://user-images.githubusercontent.com/88900482/130287350-8175c75a-4065-4f4d-ab6b-f6c3e8ab263d.PNG">

2) Phase Response i.e Vo-ph
<img width="876" alt="VOph-AC" src="https://user-images.githubusercontent.com/88900482/130287374-d6f46cc4-0f6e-4399-a0eb-017c5a781fe3.PNG">

3) All AC Response of OPAMP1
<img width="878" alt="opamp1-AC-Resp" src="https://user-images.githubusercontent.com/88900482/130287970-b1949a3f-873d-4ea8-90af-07356268da8b.PNG">

## Dual Stage OPAMP
### Transient Response
Run the following file in ngspice: opamp2_tran.spice

1) Vinp, Vinm Waveforms
<img width="868" alt="Vin-tran" src="https://user-images.githubusercontent.com/88900482/130287567-9cfc3728-4d51-4f84-a56c-f71e3167649c.PNG">

2) Vout waveform
<img width="878" alt="Vout-tran" src="https://user-images.githubusercontent.com/88900482/130287597-8f22aa3b-eda8-46aa-95bb-41b2ed678176.PNG">

### AC Response
Run the following file in ngspice: opamp2_ac.spice

1) Magnitude Response i.e. VodB
<img width="876" alt="opamp2_AC-mag_res" src="https://user-images.githubusercontent.com/88900482/130287719-117cb295-2d9b-4cad-82f7-2fb370f8bbc7.PNG">

2) Phase Response Vout-ph
<img width="875" alt="opamp2-AC-Ph-Res" src="https://user-images.githubusercontent.com/88900482/130287767-eff4a4db-afab-443c-a475-ad30fdbd437d.PNG">

3) Phase Margin Plot Vout-PM
<img width="877" alt="opamp2-AC-PM" src="https://user-images.githubusercontent.com/88900482/130287784-ea5c4ec1-8b6e-4697-9691-99effbd20cf7.PNG">

4) All AC Response
<img width="914" alt="Opamp2_AC_Res" src="https://user-images.githubusercontent.com/88900482/130287875-db3e9379-5af6-4ca3-85f8-f5bfe4da26e4.PNG">

# Further Work
From the postlayout transient response of Two stage opamp it can be obsereved that the negative peak of vout is flattened. This results in reduction of overall voltage swing at the output. So with proper design this problem can be solved.

# Contributors
1) Mrs. Madhuri H. Kadam, Assistant Professor, Shree L. R. Tiwari college of Engineering, Mira Rd (E) - madhurib.saksham@gmail.com
2) Kunal Ghosh, Co-Founder of VLSI System Design (VSD) Corp. Pvt. Ltd. - kunalghosh@gmail.com

# Acknowledgements
Kunal Ghosh, Co-Founder of VLSI System Design (VSD) Corp. Pvt. Ltd. - kunalghosh@gmail.com
