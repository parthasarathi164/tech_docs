# Simulation model of a hydraulic circuit for operating DAC using 4/3 DCV (Tandem centre config.) in MATLAB Simulink (Simscape)

**Tool:** MATLAB/Simulink Simscape

## Abstract

This project focuses on the development and simulation of a physically accurate electro-hydraulic circuit using the MATLAB/Simulink Simscape environment. The simulation goes beyond basic schematic representation by incorporating detailed mathematical sizing and physical modelling of system components. The primary objective is to design and analyse a hydraulic power system consisting of a three-phase induction motor driving a variable displacement pump, integrated with a 4/3 directional control valve operating in a tandem center configuration to control a double-acting hydraulic cylinder. The model is designed to meet a target flow rate of 100 L/min under a maximum operating pressure of 200 bar.

## 1. Introduction

This project focuses on the modelling and simulation of an electro-hydraulic system using MATLAB/Simulink Simscape. The system is driven by a three-phase induction motor coupled to a variable displacement pump, designed to deliver 100 L/min of flow at a maximum pressure of 200 bar. A 4/3 directional control valve with a tandem center configuration is used to control a double-acting hydraulic cylinder. In the neutral position, the pump unloads to the tank, reducing energy loss while holding the actuator stationary. When actuated, the valve directs flow to achieve controlled extension and retraction of the cylinder. The simulation emphasizes accurate component sizing, stable physical modelling, and realistic system behaviour.

### 1.1 Aim and Objective

The primary aim of this project is to design, model, and validate a high-efficiency hydraulic power system that uses a regenerative circuit configuration in the MATLAB/Simulink environment.

**Specific Objectives:**
* To design a system to deliver a flow rate of 100 L/min at a maximum pressure of 200 bar.
* To model the main hydraulic components accurately, including the variable displacement pump, 4/3 directional control valve, and double-acting cylinder.
* To integrate an electro-hydraulic system using MATLAB Simscape with a three-phase motor, pump, DCV, and hydraulic cylinder.
* To analyse system performance by studying pressure, flow, motor speed, and cylinder motion during neutral, extension, and retraction modes.
* To ensure stable operation while meeting design limits.

## 2. Simulink Model and Component Description

### 2.1 Overview of the Simulation Environment
The simulation is developed in MATLAB/Simulink using a modular modelling approach to represent an electro-hydraulic circuit. The system is built using Simscape physical components to model the three-phase induction motor, variable displacement pump, directional control valve, and double-acting hydraulic cylinder. This physical modelling approach ensures realistic interaction between the electrical, mechanical, and hydraulic domains.

To ensure numerical stability and accurate physical behaviour, the hydraulic fluid is modelled with limited compressibility by including a small percentage of entrained air. Proper reference connections and solver configuration are applied to prevent hydraulic lock and pressure singularities.

### 2.2 Variable Displacement Pump
The variable displacement hydraulic pump acts as the primary power source of the system and is driven by a three-phase induction motor to deliver the required hydraulic flow of 100 L/min.  The pump output is regulated to operate safely within a maximum pressure limit of 200 bar, while an external pressure relief valve ensures system stability during valve neutral and actuated operating conditions.

**Working:**
The variable displacement pump converts the motor’s mechanical rotation into hydraulic flow. By changing its internal displacement, it increases or decreases the flow supplied to the circuit based on system demand. When pressure reaches the set limit, excess flow is relieved back to the tank to protect the system and ensure stable operation.

### 2.3 4/3 DCV Tandem Centre Configuration
A 4/3 Directional Control Valve (DCV) functions as the main fluid distributor within a hydraulic circuit. It has four ports and three different spool positions. It manages the flow direction to an actuator, allowing for extension, retraction, or a neutral "hold" state.

**Working:**
In the tandem centre configuration , when the valve is in its neutral (centre) position, the pressure port P is directly connected to the tank port T, while ports A and B are blocked. This allows the pump flow to unload back to the tank at very low pressure, reducing power losses and heating, while the hydraulic cylinder remains stationary and locked in position. When the spool is shifted, the valve directs pressurized fluid from P to either A or B, causing the double-acting cylinder to either extend or retract.

### 2.4 Double Acting Cylinder
A double-acting cylinder acts as the system's mechanical actuator by converting hydraulic fluid energy into two-way linear motion. Unlike single-acting models, it uses fluid pressure to extend and retract the piston. 

**Working:**
Fluid enters port A (cap end) or port B (rod end) depending on the position of the directional control valve. When pressurized fluid is supplied to the cap end, the piston and rod extend, while fluid from the rod end returns to the tank. Reversing the flow causes pressurized fluid to act on the rod end, resulting in piston retraction. The generated force is given by $F=P \times A$, where $P$ is hydraulic pressure and $A$ is the effective piston area.

### 2.5 Induction Motor
An induction motor is an AC electric motor that converts electrical energy into mechanical energy using electromagnetic induction. Three-phase induction motors are widely used in industrial applications due to their reliable and continuous operation. 

**Working:**
When a three-phase AC supply is given to the stator, it creates a rotating magnetic field. This magnetic field cuts the rotor conductors and induces an electric current in the rotor, producing electromagnetic force. This force generates torque, causing the rotor to start rotating in the same direction as the magnetic field.

### 2.6 Hydraulic Fluid and Tank
**Hydraulic Fluid:**
The fluid used follows the DIN 51524 standard and is mineral-oil based. It ensures smooth power transmission, proper lubrication, and protects system parts from wear and corrosion.

**Tank:**
This block models a storage tank in an isothermal liquid network with constant pressurization. The block models the hydrostatic pressure difference between the liquid surface and the inlets and pressure losses at the inlets.

### 2.7 Circuit Valves
**Check Valve:**
A check valve allows fluid to flow in only one direction and automatically blocks reverse flow. In the circuit, it helps maintain system stability, protects the pump during shutdown or pressure drops, and ensures safe operation.

**Pressure Relief Valve:**
This is a safety component used to limit the maximum pressure.  When system pressure rises above the preset relief pressure, the valve opens automatically and diverts excess fluid from the pressure line back to the tank.

### 2.8 Sensors
**Pressure Sensor:**
Used to measure the hydraulic pressure at specific points. It senses the fluid pressure and converts it into a corresponding physical signal, allowing real-time observation of pressure variations.

**Flow Rate Sensor:**
Installed in series with the hydraulic line, this sensor measures the rate at which fluid flows through the circuit. It helps verify proper pump operation and valve functioning.

### 2.9 GUI: Piston Visualization Module
This visualization module consists of two MATLAB functions developed to animate the motion of the hydraulic piston.

**Start Function (`startPistonGUI`):**
Initializes the graphical user interface by drawing the cylinder, the piston head, and a calibrated position scale in centimetres. It stores the handles of the graphical objects using `setappdata`.

```matlab
function startPistonGUI(stroke)
% startPistonGUI(stroke)
% Create piston GUI. stroke in meters (default 0.30)

if nargin<1 || isempty(stroke), stroke = 0.30;
end

% Visual parameters
pistonWidth = 0.05;   % visual piston width (m)
figW = 640; figH = 260;
% Create figure
fig = figure('Name','Piston GUI','NumberTitle','off', ...
    'MenuBar','none','ToolBar','none','Resize','off');
fig.Position(3:4) = [figW figH];
% store important values in appdata
setappdata(0,'pistonStroke',stroke);
setappdata(0,'pistonWidth',pistonWidth);
setappdata(0,'pistonFig',fig);

% Main axis (cylinder)
ax = axes('Parent',fig,'Position',[0.08 0.45 0.86 0.45]);
hold(ax,'on'); axis(ax,'off');
xlim(ax,[0 stroke]); ylim(ax,[-0.12 0.12]);

% Cylinder body
rectangle(ax,'Position',[0 -0.05 stroke 0.10], 'EdgeColor','k','LineWidth',2);
% Piston rectangle (initial at 0)
pRect = rectangle(ax,'Position',[0 -0.06 pistonWidth 0.12],...
    'FaceColor',[0.1 0.6 0.9],'EdgeColor','k');
% rod visual
plot(ax,[stroke-0.02 stroke+0.02],[0 0],'k','LineWidth',2);

% Scale axis (below) showing ticks in cm
ax2 = axes('Parent',fig,'Position',[0.08 0.18 0.86 0.18]);
hold(ax2,'on'); box(ax2,'off');
xlim(ax2,[0 stroke]); ylim(ax2,[0 1]);
set(ax2,'YTick',[]);

% Create tick marks and labels in cm:
nTicks = 7;
% adjust number of ticks
tickVals = linspace(0,stroke,nTicks);
tickLabels = arrayfun(@(x) sprintf('%.0f', x*100), tickVals,'uni',false); % cm
set(ax2,'XTick',tickVals,'XTickLabel',tickLabels);
% baseline and marker
plot(ax2,[0 stroke],[0.5 0.5],'k','LineWidth',1);
marker = plot(ax2,[0 0],[0.15 0.85],'r','LineWidth',2);
% numeric text showing front-edge position (meters)
txt = uicontrol('Parent',fig,'Style','text','Units','normalized', ...
    'Position',[0.08 0.02 0.86 0.12],'String','Position (front): 0.000 m', ...
    'FontSize',11,'FontWeight','bold','HorizontalAlignment','center');
% Save handles to appdata
setappdata(0,'pistonAx',ax);
setappdata(0,'pistonRect',pRect);
setappdata(0,'pistonMarker',marker);
setappdata(0,'pistonTxt',txt);
setappdata(0,'pistonTickVals',tickVals);    % optional storing

drawnow;
end
```

**Update Function (`updatePistonGUI`):**

Called repeatedly during the simulation to animate piston movement in real time. It limits the displacement within the physical stroke length and updates the piston rectangle, scale indicator, and numeric position display accordingly.

Matlab

```
function updatePistonGUI(pos)
% updatePistonGUI(pos)  pos in meters = piston *base* position (left edge)

% retrieve handles & params
fig = getappdata(0,'pistonFig');
if isempty(fig) || ~isvalid(fig), return; end

stroke = getappdata(0,'pistonStroke');
pistonWidth = getappdata(0,'pistonWidth');
pRect = getappdata(0,'pistonRect');
marker = getappdata(0,'pistonMarker');
txt = getappdata(0,'pistonTxt');
if isempty(pRect) || ~isvalid(pRect), return; end
if isempty(pos) || ~isnumeric(pos), return; end

% clamp base position (left edge)
pos = double(pos);
pos = max(0, min(pos, stroke - pistonWidth));

% compute front-edge (leading) position and clamp to stroke
frontPos = pos + pistonWidth;
frontPos = min(frontPos, stroke);

% update piston rect (base pos)
set(pRect,'Position',[pos -0.06 pistonWidth 0.12]);
% update marker at front edge (on the cm-scale axis)
set(marker,'XData',[frontPos frontPos]);
% update numeric string to display front edge in meters (3 decimals)
set(txt,'String',sprintf('Position (front): %.3f m', frontPos));

drawnow limitrate;
end
```

### 2.10 Working Sequence of the Simulink Model

The hydraulic system starts with a three-phase induction motor driving a variable displacement pump, which converts mechanical energy into hydraulic energy. The pressurized fluid reaches a 4/3 directional control valve (DCV) with a tandem centre configuration.

1. **Neutral Position:** The pressure port is connected to the tank, allowing the pump to unload at low pressure while blocking both actuator ports.
2. **Actuation:** When the DCV is actuated, oil is directed to either side of the double-acting cylinder to produce extension or retraction.
3. **Monitoring:** Pressure and flow sensors continuously monitor the system and provide data for analysis.

## 3. Results and Discussion

### 3.1 Overview of Simulation Parameters

The simulation is configured with fixed parameters for consistent operation. The pump delivers 100 L/min with a maximum pressure limit of 200 bar. Hydraulic fluid properties are selected to ensure stable and realistic simulation results.

### 3.2 System Performance Analysis

3.2.1 Cylinder Output Scope

The plotted graph represents the piston position versus time for the double-acting cylinder.

- **Neutral/Hold:** When the valve is in the centre position, the graph remains flat, indicating that the piston position is constant and there is no motion. The pump is unloaded to the tank.
- **Extension:** When the DCV is shifted to the extension position, the piston starts moving outward, seen on the graph as a positive slope.
- **Retraction:** Upon switching the DCV to the retraction position, pressurized fluid is supplied to the rod end, causing the piston to move back. This appears on the graph as a negative slope.

3.2.2 GUI Output

The GUI shows the real-time position of a double-acting hydraulic cylinder.

- The blue block represents the piston, and the horizontal scale spans the 0–0.30 m stroke.
- Shifting the 4/3 directional control valve to extension moves the piston toward the 0.30 m limit, while the tandem-center position holds it still.
- During retraction, the piston moves back toward 0 m. The GUI enforces stroke limits to prevent overtravel.

## 4. Conclusion and Future Scope

This project successfully demonstrates the modelling and simulation of an electro-hydraulic circuit using MATLAB/Simulink Simscape. The results validate correct interaction between the three-phase induction motor, variable displacement pump, 4/3 directional control valve with tandem center configuration, and double-acting hydraulic cylinder. The simulation clearly shows pump unloading during the valve neutral position, controlled pressure build-up during actuation, and smooth cylinder extension and retraction.

Proper component sizing, reference grounding, and solver configuration ensured stable operation and realistic system behaviour, confirming the effectiveness of Simscape for physical hydraulic system analysis.

**Future Scope:**

- Incorporating non-ideal fluid properties such as viscosity, leakage, and temperature-dependent bulk modulus.
- Implementing closed-loop control strategies, such as PID control for valve spool positioning.
- Thermal modelling to analyse heat generation due to pressure losses.
