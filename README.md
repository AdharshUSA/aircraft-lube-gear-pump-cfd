# Lubrication Gear Pump in an Aircraft Accessory Gearbox: Analytical and CFD Study

Final year project for the B.E. in Mechanical Engineering (course ME8811), Meenakshi Sundararajan Engineering College, Anna University, June 2022. Carried out at the Combat Vehicles Research and Development Establishment (CVRDE), DRDO, Chennai.

**Tools:** MATLAB, SolidWorks, ANSYS Workbench (SpaceClaim, Meshing, CFX)

## Problem

The accessory gearbox of an aircraft is driven by the engine and carries a lubrication gear pump. The gearbox was to be modified so that the pump's drive speed would increase. Before changing the pump, the team needed to understand how its gear geometry sets the flow it delivers, and where the flow is lost inside it.

## Approach

1. **Analytical model in MATLAB.** A script built from the standard displacement and discharge relations for external spur gear pumps. It varies one gear parameter at a time (module, number of teeth, addendum diameter, face width, pressure angle) at the existing and the proposed drive speed, plots theoretical discharge, and computes the slope of each curve to rank how strongly each parameter drives flow.
2. **3D design in SolidWorks.** Gears, casing and the gear and casing assembly, built from the existing pump's dimensions with an involute tooth profile.
3. **CFD in ANSYS CFX.** A transient 3D simulation of the lubricating oil in the pump using the immersed solid method, SST turbulence model and pressure boundary conditions at inlet and outlet. Pressure, velocity and turbulent kinetic energy fields were examined, along with velocity vectors in the tooth gaps.
4. **Loss study.** The CFD fields were used to point out where internal losses arise and what to change to limit them.

## What the study found

- **Sensitivity of discharge to geometry.** Module and tip (addendum) diameter act non-linearly on discharge, number of teeth and face width act roughly linearly, and pressure angle has comparatively little effect. Discharge is proportional to speed, so the displacement per revolution is a fixed property of a given pump.
- **Pressure.** In the analytical comparison, enlarging module, tooth count or face width at the same power lowers the pressure the pump develops.
- **Where flow is lost.** The CFD shows eddies forming between teeth and leakage over the tooth tips back toward the previous tooth. As friction heats the oil and its viscosity drops, tip leakage grows. The report also lists viscous friction in the shaft bearings, at the tooth tips, and between the gear faces and the bushing blocks as loss sources.
- **Casing.** The inlet port is larger than the outlet port, and the velocity field shows higher velocity at the outlet.

## Solver notes

The same problem was first attempted in ANSYS Fluent with dynamic meshing. It failed with negative cell volume errors because the moving gear boundaries needed a very fine mesh. The immersed solid approach in CFX handled the rotating gears on a coarser mesh without remeshing, so the study was run there. The approach is suited to pressure-dominated flow and does not resolve boundary layers or cavitation.

## Limitations

- The CFD covers a single operating case at the existing drive speed and a short transient window of about one gear revolution. The higher speed proposed for the modified gearbox was only evaluated in the analytical model.
- The CFD flow at the inlet and outlet differ noticeably, and the CFD flow falls well below the analytical estimate. That points to a run that had not settled to a periodic state, so the CFD values are better read as flow patterns than as predicted flow rates.
- There is no mesh independence study and no comparison with test data.
- Design dimensions, operating conditions and numerical results from the work at CVRDE are not published here.

## Team

Adharsh Rajasekar, Rishabh Paliwal P and Sooraj S. College supervisor: Mr. M. Vadivel, Assistant Professor, Department of Mechanical Engineering. The work was guided by scientists at CVRDE.
