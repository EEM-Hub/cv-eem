---
source: https://en.wikipedia.org/wiki/Autonomous_driving
fetched: 2026-06-21
---

Automation for various purposes of vehicles For vehicles relying completely either on automation or remote control, see [Uncrewed vehicle](./Uncrewed_vehicle). "Intelligent car" redirects here. For the European Commission policy, see [Intelligent Car Initiative](./Intelligent_Car_Initiative). 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0e/The_ESA_Seeker_autonomous_rover_during_tests_at_Paranal.jpg/500px-The_ESA_Seeker_autonomous_rover_during_tests_at_Paranal.jpg)](./File:The_ESA_Seeker_autonomous_rover_during_tests_at_Paranal.jpg)The [ESA](./ESA) Seeker autonomous rover during tests at [Paranal](./Paranal_Observatory)[[1]](./Vehicular_automation#cite_note-1) [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f5/Automated_Vehicle_System_Technology_Hierarchy.png/250px-Automated_Vehicle_System_Technology_Hierarchy.png)](./File:Automated_Vehicle_System_Technology_Hierarchy.png)Automated vehicle system technology hierarchy 
| Part ofa serieson |
| --- |
| Self-driving carsand self-driving vehicles |
|  |
| Enablers |
| Assured clear distance aheadAutonomous racingDatasetsLane centeringPedestrian crash avoidance mitigationVehicle infrastructure integration |
| Topics |
| Automatic parkingHistoryImpactPlatoonRegulationLiabilityRobotaxiSelf-driving truckTunnel problem |
| Related topics |
| Automatic train operationUnmanned surface vehicleVehicular automation |
| vte |

 
| Part ofa serieson |
| --- |
| Automation |
|  |
| Automation in general |
| BankingBuildingHomeHighway systemLaboratoryLibraryBroadcastMixPool cleanerPop musicReasoningSemi-automationTelephoneAttendantSwitchboardTeller machineVehicularVending machine |
| Roboticsandrobots |
| DomesticVacuum cleanerRoombaLawn mowerGuided vehicleIndustrialConstructionPaintOperational design domain |
| Impact of automation |
| ManumationOut-of-the-loop performance problemBiasSelf-driving carsTechnological unemploymentJobless recoveryPost-work societyThreat |
| Trade shows and awards |
| ASP-DACDACDATEIEEE Robotics and Automation AwardICCAD |
| vte |

 

**Vehicular automation** is using technology to assist or replace if fully autonomous, as in [[autonomous robot]]; vs. [[telerobotic]] operation or [[human&#x2D;in&#x2D;the&#x2D;loop]] assisted operation  the operator of a [vehicle](./Vehicle) such as a car, truck, aircraft, rocket, military vehicle, or boat.[[2]](./Vehicular_automation#cite_note-tvt2-2)[[3]](./Vehicular_automation#cite_note-tro-3)[[4]](./Vehicular_automation#cite_note-4)[[5]](./Vehicular_automation#cite_note-5)[[6]](./Vehicular_automation#cite_note-6) Assisted vehicles are *semi-autonomous*, whereas vehicles that can travel without a human operator are [*autonomous*](./Autonomous_robot).[[3]](./Vehicular_automation#cite_note-tro-3) The degree of autonomy may be subject to various constraints such as conditions. Autonomy is enabled by [advanced driver-assistance systems](./Advanced_driver-assistance_systems) (ADAS) of varying capacity.

 

Related technology includes advanced software, maps, vehicle changes, and outside vehicle support.  The benefits of viewing automated driving from a sociotechnical systems perspective has been discussed.[[7]](./Vehicular_automation#cite_note-7)

 

Autonomy presents varying issues for road, air, and marine travel. Roads present the most significant complexity given the unpredictability of the driving environment, including diverse road designs, driving conditions, traffic, obstacles, and geographical/cultural differences.[[8]](./Vehicular_automation#cite_note-tcas-8)

 

Autonomy implies that the vehicle is responsible for all perception, monitoring, and control functions.[[9]](./Vehicular_automation#cite_note-9)

  

## SAE autonomy levels

 Main article: [Self-driving car § automation-levels](./Self-driving_car#automation-levels) Further information: [Automatic train operation § Grades of automation](./Automatic_train_operation#Grades_of_automation) 

The SAE classification of levels is based on the role of the driver, rather than the vehicle's capabilities, although these are related in the form of a "driving mode" (also known as a "driving [scenario](./Scenario_(vehicular_automation))"). The mode is determined by both an [operational design domain](./Operational_design_domain) (ODD) and a "dynamic driving requirement".  The ODD is the circumstance in which the car is driving, and the driving requirement is what the system must do while remaining safe within the boundaries of that ODD. These two things define the SAE level.[[10]](./Vehicular_automation#cite_note-Self-driving_car_SAE_definitions2-10)

 
| Mode | Level | Summary | Description | Responsibility for |
| --- | --- | --- | --- | --- |
| Direction & speed | Monitoring environment | Fallback |
| N/A | 0 | No Automation | Full-time performance by the driver of all aspects of driving, even when "enhanced by warning or intervention systems" | Driver | Driver | Driver |
| Some | 1 | Driver assistance | Driving mode-specific control by an ADAS of either steering or speed | ADAS uses information about the driving environment; driver is expected to perform all other driving tasks. |
| System |
| 2 | Partial automation | Driving mode-specific execution by one or more ADAS for both steering and speed |
| 3 | Conditional automation | Driving mode-specific control by an ADAS of all aspects of driving | Driver must appropriately respond to a request to intervene. | System |
| Many | 4 | High automation | If a driver does not respond appropriately to a request to intervene, the car can stop safely. | System |
| All | 5 | Full automation | System controls the vehicle under all conditions and circumstances. |

   

## Technology

 

### Software

 

Autonomous vehicle software generally contains several different modules that work together to enable self-driving capabilities.[[11]](./Vehicular_automation#cite_note-11)[[12]](./Vehicular_automation#cite_note-auto-12)[[13]](./Vehicular_automation#cite_note-13) The perception module ingests and processes data from various sensors, such [cameras](./Camera), [LIDAR](./Lidar), [RADAR](./RADAR), and ultrasonic [SONAR](./SONAR), to create a comprehensive understanding of the vehicle's surroundings.[[14]](./Vehicular_automation#cite_note-14) The localization module uses 3D [point cloud](./Point_cloud) data, [GPS](./GPS), [IMU](./Inertial_measurement_unit), and mapping information to determine the vehicle's precise position, including its orientation, velocity, and [angular rate](./Angular_rate).[[12]](./Vehicular_automation#cite_note-auto-12)[[15]](./Vehicular_automation#cite_note-15) The planning module takes inputs from both perception and localization to compute actions to take, such as velocity and steering angle outputs.[[16]](./Vehicular_automation#cite_note-16) These modules are typically supported by [machine learning](./Machine_learning) algorithms, particularly [deep neural networks](./Deep_neural_networks),[[17]](./Vehicular_automation#cite_note-:8-17) which enable the vehicle to detect objects, interpret traffic patterns,[[18]](./Vehicular_automation#cite_note-18) and make real-time decisions.[[19]](./Vehicular_automation#cite_note-19) Furthermore, modern autonomous driving systems increasingly employ [sensor fusion](./Sensor_fusion) techniques that combine data from multiple sensors to improve accuracy and reliability in different environmental conditions.[[20]](./Vehicular_automation#cite_note-20)[[21]](./Vehicular_automation#cite_note-21)

 

### Perception

 

The perception system is responsible for observing the environment. It must identify everything that could affect the trip, including other vehicles, pedestrians, cyclists, their movements, road conditions, obstacles, and other issues.[[22]](./Vehicular_automation#cite_note-:9-22) Various makers use cameras, [radar](./Radar), [lidar](./Lidar), [sonar](./Sonar), and microphones that can collaboratively minimize errors.[[22]](./Vehicular_automation#cite_note-:9-22)[[23]](./Vehicular_automation#cite_note-23)

 

### Navigation

 

Navigation systems are a necessary element in autonomous vehicles. The [Global Positioning System](./Global_Positioning_System) (GPS) is used for navigation by air, water, and land vehicles, particularly for off-road navigation.

 

For road vehicles, two approaches are prominent. One is to use maps that hold data about lanes and intersections, relying on the vehicle's perception system to fill in the details. The other is to use highly detailed maps that reduce the scope of real-time decision-making but require significant maintenance as the environment evolves.[[17]](./Vehicular_automation#cite_note-:8-17) Some systems crowdsource their map updates, using the vehicles themselves to update the map to reflect changes such as construction or traffic used by the entire vehicle fleet.[[24]](./Vehicular_automation#cite_note-24)

 

Another potential source of information is the environment itself. Traffic data may be supplied by roadside monitoring systems and used to route vehicles to best use a limited road system.[[25]](./Vehicular_automation#cite_note-:11-25) Additionally, modern [GNSS enhancement](./GNSS_enhancement) technologies, such as [real-time kinematic](./Real-time_kinematic_positioning) (RTK) and [precise point positioning](./Precise_Point_Positioning) (PPP), enhance the accuracy of vehicle positioning to sub-meter level precision, which is crucial for autonomous navigation and decision-making.[[26]](./Vehicular_automation#cite_note-26)

 

## History

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/7e/Stanford_Cart_and_Hydraulic_Arm_%285900601910%29.jpg/250px-Stanford_Cart_and_Hydraulic_Arm_%285900601910%29.jpg)](./File:Stanford_Cart_and_Hydraulic_Arm_(5900601910).jpg)Stanford Cart and Hydraulic Arm 

The *"Stanford Cart",* created by [Hans Moravec](./Hans_Moravec) in the late 1970s while he was a graduate student, was the first experimental autonomous vehicle. It was a precursor to both [NASA](./NASA)'s Moon and Mars Lander projects as it was known at the time that  radio signal lag times would have made anything other than autonomous control impractical. The box rested on 4 bicycle wheels, and had a camera, battery and a radio antenna connecting it wirelessly to a remote computer. It could also be steered remotely.[[27]](./Vehicular_automation#cite_note-27) Morovic was able to get the Cart to navigate around large obstacles in a 100 foot long room, albeit it would take 5 hours as the cart would frequently stop as the computer processed images which it analyzed and then responded with navigation instructions.

 

Approximately 20 years later the [Robotics Lab](./Navlab) at [Carnegie Mellon University](./Carnegie_Mellon_University) developed [ALVINN](./Navlab#ALVINN) (Autonomous Land vehicle in a Neural Network) a vehicle with 3 onboard [Sun Microsystems](./Sun_Microsystems) computers that, using a camera and a laser range finder, could slowly drive itself down a road by monitoring the white divider line.[[28]](./Vehicular_automation#cite_note-28)[[29]](./Vehicular_automation#cite_note-29)

 

Automated vehicles in European Union legislation refer specifically to road vehicles (car, truck, or bus).[[30]](./Vehicular_automation#cite_note-30) For those vehicles, a specific difference is legally defined between [advanced driver-assistance system](./Advanced_driver-assistance_system) and autonomous/automated vehicles, based on liability differences.

 

[AAA Foundation for Traffic Safety](./AAA_Foundation_for_Traffic_Safety) tested two automatic emergency braking systems: some designed to prevent crashes and others that aim to make a crash less severe. The test looked at popular models like the 2016 [Volvo XC90](./Volvo_XC90), [Subaru Legacy](./Subaru_Legacy), [Lincoln MKX](./Lincoln_MKX), [Honda Civic](./Honda_Civic), and [Volkswagen Passat](./Volkswagen_Passat). Researchers tested how well each system stopped when approaching moving and nonmoving targets. It found that systems capable of preventing crashes reduced vehicle speeds by twice that of the systems designed to mitigate crash severity. When the two test vehicles traveled within 30 mph of each other, even those designed to lessen crash severity avoided crashes 60 percent of the time.[[31]](./Vehicular_automation#cite_note-31)

 

### Sartre

 

The SAfe Road TRains for the Environment (Sartre) project's goal was to enable platooning, in which a line of cars and trucks (a "train") follow a human-driven vehicle. Trains were predicted to provide comfort and allow the following vehicles to travel safely to a destination. Human drivers encountering a train could join and delegate driving to the human driver.[[32]](./Vehicular_automation#cite_note-32)

 

### Tests

 

Self-driving Uber vehicles were tested in Pittsburgh, Pennsylvania. The tests were paused after an autonomous car killed a woman in Arizona.[[33]](./Vehicular_automation#cite_note-33)[[34]](./Vehicular_automation#cite_note-34) Automated busses have been tested in California.[[35]](./Vehicular_automation#cite_note-35) In San Diego, California, an automated bus test used magnetic markers. The longitudinal control of automated truck platoons used [millimeter wave](./Millimeter_wave) radio and radar. Waymo and [Tesla](./Tesla_Motors) have conducted tests. [Tesla FSD](./Tesla_Autopilot) allows drivers to enter a destination and let the car take over.

 

### Risks and liabilities

 See also: [Computer security § Automobiles](./Computer_security#Automobiles), and [Autonomous car liability](./Autonomous_car_liability) 

Ford offers Blue Cruise, technology that allows [geofenced](./Geofence) cars to drive autonomously.[[36]](./Vehicular_automation#cite_note-computer_world-36)

 

Drivers are directed to stay attentive, and safety warnings are implemented to alert the driver when corrective action is needed.[[37]](./Vehicular_automation#cite_note-Automated_Vehicle_Technology_2014-37) [Tesla, Incorporated](./Tesla,_Inc.) has one recorded incident that resulted in a fatality involving the automated driving system in the Tesla Model S.[[38]](./Vehicular_automation#cite_note-Tesla_Loss-38) The accident report reveals the accident was a result of the driver being inattentive and the autopilot system not recognizing the obstruction ahead.[[38]](./Vehicular_automation#cite_note-Tesla_Loss-38) Tesla has also had multiple instances where the vehicle crashed into a garage door. According to the book "The Driver in the Driverless Car: How Your Technology Choices Create the Future," Tesla automatically performs an update overnight. The morning after the update, the driver used his app to "summon" his car, and it crashed into his garage door.

 

Another flaw with automated driving systems is that unpredictable events, such as weather or the driving behavior of others, may cause fatal accidents due to sensors that monitor the surroundings of the vehicle not being able to provide corrective action.[[37]](./Vehicular_automation#cite_note-Automated_Vehicle_Technology_2014-37)

 

To overcome some of the challenges for automated driving systems, novel methodologies based on virtual testing, traffic flow simulation and digital prototypes have been proposed,[[39]](./Vehicular_automation#cite_note-39) especially when novel algorithms based on Artificial Intelligence approaches are employed which require extensive training and validation data sets.

 

Implementing automated driving systems poses the possibility of changing built environments in urban areas, such as expanding the suburban regions due to the increased ease of mobility.[[40]](./Vehicular_automation#cite_note-:7-40)

 

## Challenges

 

Around 2015, several self-driving car companies including Nissan and Toyota promised self-driving cars by 2020. However, the predictions turned out to be far too optimistic.[[41]](./Vehicular_automation#cite_note-:15-41)

 

There are still many obstacles in developing fully autonomous Level 5 vehicles, which is the ability to operate in any conditions. Currently, companies are focused on Level 4 automation, which is able to operate under certain environmental circumstances.[[41]](./Vehicular_automation#cite_note-:15-41)

 

There is still debate about what an autonomous vehicle should look like. For example, whether to incorporate lidar to autonomous driving systems is still being argued. Some researchers have come up with algorithms using camera-only data that achieve the performance that rival those of lidar. On the other hand, camera-only data sometimes draw inaccurate bounding boxes, and thus lead to poor predictions. This is due to the nature of superficial information that [stereo cameras](./Stereo_camera) provide, whereas incorporating lidar gives autonomous vehicles precise distance to each point on the vehicle.[[41]](./Vehicular_automation#cite_note-:15-41)

 

### Technical challenges

 
- Software Integration: Because of the large number of sensors and safety processes required by autonomous vehicles, software integration remains a challenging task. A robust autonomous vehicle should ensure that the integration of hardware and software can recover from component failures.[[42]](./Vehicular_automation#cite_note-:16-42)
- Prediction and trust among autonomous vehicles: Fully autonomous cars should be able to anticipate the actions of other cars like humans do. Human drivers are great at predicting other drivers' behaviors, even with a small amount of data such as eye contact or hand gestures. In the first place, the cars should agree on traffic rules, whose turn it is to drive in an intersection, and so on. This scales into a larger issue when there exists both human-operated cars and self-driving cars due to more uncertainties. A robust autonomous vehicle is expected to improve on understanding the environment better to address this issue.[[42]](./Vehicular_automation#cite_note-:16-42)
- Scaling up: The coverage of autonomous vehicles testing could not be accurate enough. In cases where heavy traffic and obstruction exist, it requires faster response time or better tracking algorithms from the autonomous vehicles. In cases where unseen objects are encountered, it is important that the algorithms are able to track these objects and avoid collisions.[[42]](./Vehicular_automation#cite_note-:16-42)

 

These features require numerous sensors, many of which rely on [micro-electro-mechanical systems](./MEMS) (MEMS) to maintain a small size, high efficiency, and low cost. Foremost among MEMS sensors in vehicles are [accelerometers](./Accelerometer) and [gyroscopes](./Gyroscope) to measure acceleration around multiple orthogonal axes—critical to detecting and controlling the vehicle's motion.

 

### Societal challenges

 

One critical step to achieve the implementation of autonomous vehicles is the acceptance by the general public. It provides guidelines for the automobile industry to improve their design and technology. Studies have shown that many people believe that using autonomous vehicles is safer, which underlines the necessity for the automobile companies to assure that autonomous vehicles improve safety benefits. The TAM research model breaks down important factors that affect the consumer's acceptance into: usefulness, ease to use, trust, and social influence.[[43]](./Vehicular_automation#cite_note-:17-43)

 
- The usefulness factor studies whether or not autonomous vehicles are useful in that they provide benefits that save consumers' time and make their lives simpler. How well the consumers believe autonomous vehicles will be useful compared to other forms of transportation solutions is a determining factor.[[43]](./Vehicular_automation#cite_note-:17-43)
- The ease to use factor studies the user-friendliness of the autonomous vehicles. While the notion that consumers care more about ease to use than safety has been challenged. It still remains an important factor that has indirect effects on the public's intention to use autonomous vehicles.[[43]](./Vehicular_automation#cite_note-:17-43)
- The trust factor studies the safety, data privacy and security protection of autonomous vehicles. A more trusted system has a positive impact on the consumer's decision to use autonomous vehicles.[[43]](./Vehicular_automation#cite_note-:17-43)
- The social influence factor studies whether the influence of others would influence consumer's likelihood of having autonomous vehicles. Studies have shown that the social influence factor is positively related to behavioral intention. This might be due to the fact that cars traditionally serve as a status symbol that represents one's intent to use and his social environment.[[43]](./Vehicular_automation#cite_note-:17-43)

 

### Regulatory challenges

 See also: [Regulation of self-driving cars](./Regulation_of_self-driving_cars) 

Real-time testing of autonomous vehicles is an inevitable part of the process. At the same time, vehicular automation regulators are faced with challenges to protect public safety and yet allow autonomous vehicle companies to test their products. Groups representing autonomous vehicle companies are resisting most regulations, whereas groups representing vulnerable road users and traffic safety are pushing for regulatory barriers. To improve traffic safety, the regulators are encouraged to find a middle ground that protects the public from immature technology while allowing autonomous vehicle companies to test the implementation of their systems.[[44]](./Vehicular_automation#cite_note-44) Regulators face daunting challenges such as jurisdictional ambiguities, the rapid obsolescence of current technologies and the lack of future-looking cost-benefit data to support regulatory development.[[45]](./Vehicular_automation#cite_note-45)  There have also been proposals to adopt the aviation automation safety regulatory knowledge into the discussions of safe implementation of autonomous vehicles, due to the experience that has been gained over the decades by the aviation sector on safety topics.[[46]](./Vehicular_automation#cite_note-46)

 

## Ground vehicles

 Further information: [Unmanned ground vehicle](./Unmanned_ground_vehicle) 

In some countries, specific laws and regulations apply to road traffic motor vehicles (such as cars, bus and trucks) while other laws and regulations apply to other ground vehicles such as tram, train or automated guided vehicles making them to operate in different environments and conditions.

 

### Road traffic vehicles

 

An automated driving system is defined in a proposed amendment to Article 1 of the [Vienna Convention on Road Traffic](./Vienna_Convention_on_Road_Traffic):

 

(ab) "[Automated driving system](./Automated_driving_system)" refers to a vehicle system that uses both hardware and
software to exercise dynamic control of a vehicle on a sustained basis.

(ac) "Dynamic control" refers to carrying out all the real-time operational and tactical functions required to move the vehicle. This includes controlling the vehicle's lateral and longitudinal motion, monitoring the road environment, responding to events in the road traffic environment, and planning and signalling for manoeuvres.[[47]](./Vehicular_automation#cite_note-47)

 

This amendment will enter into force on 14 July 2022, unless it is rejected before 13 January 2022.[[48]](./Vehicular_automation#cite_note-48)

 

An automated driving feature must be described sufficiently clearly so that it is distinguished from an assisted driving feature.

— SMMT[[49]](./Vehicular_automation#cite_note-ReferenceA-49)

 

There are two clear states – a vehicle is either assisted with a driver being supported by technology or automated where the technology is effectively and safely replacing the driver.

— SMMT[[49]](./Vehicular_automation#cite_note-ReferenceA-49)

 

Ground vehicles employing automation and [teleoperation](./Teleoperation) include shipyard gantries, mining trucks, bomb-disposal robots, robotic insects, and [driverless tractors](./Driverless_tractor).

 

There are many autonomous and semi-autonomous ground vehicles being made for the purpose of transporting passengers. One such example is the free-ranging on grid ([FROG](https://nl.wikipedia.org/wiki/Free%20Ranging%20On%20Grid)) technology which consists of autonomous vehicles, a magnetic track and a supervisory system. The FROG system is deployed for industrial purposes in factory sites and has been in use since 1999 on the [ParkShuttle](./ParkShuttle), a [PRT](./Personal_rapid_transit)-style public transport system in the city of [Capelle aan den IJssel](./Capelle_aan_den_IJssel) to connect the Rivium business park with the neighboring city of [Rotterdam](./Rotterdam) (where the route terminates at the [Kralingse Zoom](./Kralingse_Zoom) metro station). The system experienced a crash in 2005[[50]](./Vehicular_automation#cite_note-50) that proved to be caused by a human error.[[51]](./Vehicular_automation#cite_note-51)

 

Applications for automation in ground vehicles include the following:

 
- [Vehicle tracking system](./Vehicle_tracking_system) system ESITrack, [Lojack](./Lojack).
- Rear-view alarm, to detect obstacles behind.
- [Anti-lock braking system](./Anti-lock_braking_system) (ABS) (also Emergency Braking Assistance ([EBA](./Emergency_brake_assist))), often coupled with [Electronic brake force distribution](./Electronic_brake_force_distribution) (EBD), which prevents the brakes from locking and losing traction while braking. This shortens stopping distances in most cases and, more importantly, allows the driver to steer the vehicle while braking.
- [Traction control system](./Traction_control_system) (TCS) actuates brakes or reduces throttle to restore traction if driven wheels begin to spin.
- [Four wheel drive](./Four_wheel_drive) (AWD) with a centre differential. Distributing power to all four wheels lessens the chances of wheel spin. It also suffers less from [oversteer](./Oversteer) and [understeer](./Understeer).
- [Electronic Stability Control](./Electronic_Stability_Control) (ESC) (also known for [Mercedes-Benz](./Mercedes-Benz) proprietary Electronic Stability Program (ESP), [Acceleration Slip Regulation](./Acceleration_Slip_Regulation) (ASR) and Electronic differential lock (EDL)). Uses various sensors to intervene when the car senses a possible loss of control. The car's control unit can reduce power from the engine and even apply the brakes on individual wheels to prevent the car from [understeering](./Understeer) or [oversteering](./Oversteer).
- [Dynamic steering response](./Dynamic_steering_response) (DSR) corrects the rate of [power steering](./Power_steering) system to adapt it to vehicle's speed and road conditions.

 

Research is ongoing and prototypes of autonomous ground vehicles exist.

 

### Cars

 See also: [Self-driving car](./Self-driving_car) 

Extensive automation for cars focuses on either introducing [robotic cars](./Robotic_cars) or modifying modern car designs to be semi-autonomous.

 

Semi-autonomous designs could be implemented sooner as they rely less on technology that is still at the forefront of research. An example is the dual mode monorail. Groups such as [RUF](./Dual-mode_transit) (Denmark) and TriTrack (USA) are working on projects consisting of specialized private cars that are driven manually on normal roads but also that dock onto a monorail/guideway along which they are driven autonomously.

 

As a method of automating cars without extensively modifying the cars as much as a [robotic car](./Robotic_car), [Automated highway systems](./Automated_highway_system) (AHS) aims to construct lanes on highways that would be equipped with, for example, magnets to guide the vehicles. Automation vehicles have auto-brakes named as Auto Vehicles Braking System (AVBS). Highway computers would manage the traffic and direct the cars to avoid crashes.

 

In 2006, The [European Commission](./European_Commission) has established a smart car development program called the *Intelligent Car Flagship Initiative*.[[52]](./Vehicular_automation#cite_note-52) The goals of that program include:

 
- [Adaptive cruise control](./Adaptive_cruise_control)
- [Lane departure warning system](./Lane_departure_warning_system)
- Project AWAKE for drowsy drivers

 

There are further uses for automation in relation to cars. These include:

 
- [Assured Clear Distance Ahead](./Assured_Clear_Distance_Ahead)
- [Adaptive headlamps](./Headlamp#Advanced_front-lighting_system_(AFS))
- [Advanced Automatic Collision Notification](./Advanced_Automatic_Collision_Notification), such as [OnStar](./OnStar)
- [Intelligent Parking Assist System](./Intelligent_Parking_Assist_System)
- [Automatic Parking](./Automatic_Parking)
- [Automotive night vision](./Automotive_night_vision) with pedestrian detection
- [Blind spot monitoring](./Blind_spot_monitoring)
- [Driver Monitoring System](./Driver_Monitoring_System)
- [Robotic car](./Robotic_car) or self-driving car which may result in less-stressed "drivers", higher efficiency (the driver can do something else), increased safety and less [pollution](./Pollution) (e.g. via completely automated [fuel](./Gasoline) control)
- [Precrash system](./Precrash_system)
- [Safe speed governing](./Assured_Clear_Distance_Ahead)
- [Traffic sign recognition](./Traffic_sign_recognition)
- Following another car on a motorway – "enhanced" or "adaptive" cruise control, as used by Ford Motor Company and Vauxhall[[53]](./Vehicular_automation#cite_note-53)
- Distance control assist – as developed by Nissan[[54]](./Vehicular_automation#cite_note-54)
- [Dead man's switch](./Dead_man's_switch) – there is a move to introduce [deadman's braking](./Deadman's_braking) into automotive application, primarily heavy vehicles, and there may also be a need to add [penalty switches](./Penalty_switch) to [cruise controls](./Cruise_control).

 

Singapore also announced a set of provisional national standards on January 31, 2019, to guide the autonomous vehicle industry. The standards, known as Technical Reference 68 (TR68), will promote the safe deployment of fully driverless vehicles in Singapore, according to a joint press release by Enterprise Singapore (ESG), Land Transport Authority (LTA), Standards Development Organisation and Singapore Standards Council (SSC).[[55]](./Vehicular_automation#cite_note-55)

 

### Shuttle

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c6/Parkshuttle.jpg/250px-Parkshuttle.jpg)](./File:Parkshuttle.jpg)Parkshuttle [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e8/Navette_Navya_MEL_2019-03.jpg/250px-Navette_Navya_MEL_2019-03.jpg)](./File:Navette_Navya_MEL_2019-03.jpg)Navya Autonom Shuttle [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Easy_Mile_EZ10.jpg/250px-Easy_Mile_EZ10.jpg)](./File:Easy_Mile_EZ10.jpg)Easymile EZ10 [![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f0/Apolong_at_Shougang_Jiaohuachang_%2820230322140939%29.jpg/250px-Apolong_at_Shougang_Jiaohuachang_%2820230322140939%29.jpg)](./File:Apolong_at_Shougang_Jiaohuachang_(20230322140939).jpg)King Long Apolong 

Since 1999, the 12-seat/10-standing [ParkShuttle](./ParkShuttle) has been operating on an 1.8 kilometres (1.1 mi) exclusive right of way in the city of [Capelle aan den IJssel](./Capelle_aan_den_IJssel) in The Netherlands. The system uses small magnets in the road surface to allow the vehicle to determine its position. The use of shared autonomous vehicles was trialed around 2012 in a hospital car park in Portugal.[[56]](./Vehicular_automation#cite_note-56) From 2012 to 2016, the [European Union](./European_Union) funded CityMobil2 project examined the use of shared autonomous vehicles and passenger experience including short term trials in seven cities. This project led to the development of the EasyMile EZ10.[[57]](./Vehicular_automation#cite_note-57)

 

In the 2010s, self-driving shuttle became able to run in mixed traffic without the need for embedded guidance markers.[[58]](./Vehicular_automation#cite_note-58) So far the focus has been on low speed, 20 miles per hour (32 km/h), with short, fixed routes for the "last mile" of journeys. This means issues of collision avoidance and safety are significantly less challenging than those for automated cars, which seek to match the performance of conventional vehicles. Many trials have been undertaken, mainly on quiet roads with little traffic or on public pathways or private roadways and specialised test sites.[*[citation needed](./Wikipedia:Citation_needed)*] The capacity of different models varies significantly, between 6-seats and 20-seats. (Above this size there are conventional buses that have driverless technology installed.)

 

In December 2016, the [Jacksonville Transportation Authority](./Jacksonville_Transportation_Authority) has announced its intention to replace the [Jacksonville Skyway](./Jacksonville_Skyway) monorail with driverless vehicles that would run on the existing elevated superstructure as well as continue onto ordinary roads.[[59]](./Vehicular_automation#cite_note-59) The project has since been named the "Ultimate Urban Circulator" or "U2C" and testing has been carried out on shuttles from six different manufacturers. The cost of the project is estimated at $379 million.[[60]](./Vehicular_automation#cite_note-60)

 

In January 2017, it was announced the [ParkShuttle](./ParkShuttle) system in the Netherlands will be renewed and expanded including extending the route network beyond the exclusive right of way so vehicles will run in mixed traffic on ordinary roads.[[61]](./Vehicular_automation#cite_note-61) The plans were delayed and the extension into mixed traffic was expected in 2021.[[62]](./Vehicular_automation#cite_note-62)

 

In July 2018, [Baidu](./Baidu) stated it had built 100 of its 8-seat [Apolong](./Apolong) model, with plans for commercial sales.[[63]](./Vehicular_automation#cite_note-63) As of July 2021, they had not gone into volume production.

 

In August 2020, it was reported there were 25 autonomous shuttle manufacturers,[[64]](./Vehicular_automation#cite_note-64) including the [2GetThere](./ParkShuttle), [Local Motors](./Local_Motors), [Navya](./Navya_SAS), [Baidu](./Baidu), [Easymile](./EasyMile_EZ10), [Toyota](./Toyota) and Ohmio.

 

In December 2020, [Toyota](./Toyota) showcased its 20-passenger "e-Palette" vehicle, which is due to be used at the [2021 Tokyo Olympic Games](./2021_Tokyo_Olympic_Games).[[65]](./Vehicular_automation#cite_note-65) Toyota announced it intends to have the vehicle available for commercial applications before 2025.[[66]](./Vehicular_automation#cite_note-66)

 

In January 2021, Navya released an investor report which predicted global autonomous shuttle sales will reach 12,600 units by 2025, with a market value of EUR 1.7 billion.[[67]](./Vehicular_automation#cite_note-67)

 

In June 2021, Chinese maker [Yutong](./Yutong) claimed to have delivered 100 models of its 10-seat Xiaoyu 2.0 autonomous bus for use in [Zhengzhou](./Zhengzhou). Testing has been carried out in a number of cities since 2019 with trials open to the public planned for July 2021.[[68]](./Vehicular_automation#cite_note-XiaoyuJune2021-68)

 

Self-driving shuttles are already in use on some private roads, such as at the Yutong factory in Zhengzhou where they are used to transport workers between buildings of the world's largest bus factory.[[69]](./Vehicular_automation#cite_note-69)

 

In Hong Kong, the police and other workers use driverless vehicles.[[70]](./Vehicular_automation#cite_note-70)

 

#### Trials

 

A large number of trials have been conducted since 2016, with most involving only one vehicle on a short route for a short period of time and with an onboard conductor. The purpose of the trials has been to both provide technical data and to familiarize the public with the driverless technology. A 2021 survey of over 100 shuttle experiments across Europe concluded that low speed – 15–20 kilometres per hour (9.3–12.4 mph) – was the major barrier to implementation of autonomous shuttle buses. The current cost of the vehicles at €280,000 and the need for onboard attendants were also issues.[[71]](./Vehicular_automation#cite_note-71)

 
|  | This list isincomplete; you can help byadding missing items.(April 2023) |
| --- | --- |

  Suggest to add more headers to the table below, such as date, name of trial (if any), geographic location, and sort each entry by time/location.  
| Company/Location | Details |
| --- | --- |
| Navya"Arma" inNeuhausen am Rheinfall | In October 2016, BestMile started trials inNeuhausen am Rheinfall, claiming to be the world's first solution for managing hybrid fleets with both autonomous and non-autonomous vehicles.[72]The test ended in October 2021.[73] |
| Local Motors "Olli" | At the end of 2016, the Olli was tested inWashington D.C.[74]In 2020, a four-month trial was undertaken at the United NationsITCILOcampus inTurin, Italyto provide transport shuttle to employees and guests within the campus.[75] |
| Navya "Autonom" | Navya claimed in May 2017 to have carried almost 150,000 passengers across Europe[76]with trials inSion,Cologne,Doha,Bordeauxand the nuclear power plant atCivauxas well asLas Vegas[77]andPerth.[78]Ongoing public trials are underway inLyon,Val ThorensandMasdar City. Other trials on private sites are underway atUniversity of Michigansince 2016,[79]atSalford Universityand theFukushima Daini Nuclear Power Plantsince 2018.[80] |
| Texas A&M | In August 2017, a driverless four seat shuttle was trialed atTexas A&Muniversity as part of its "Transportation Technology Initiative" in a project run by academics and students on the campus.[81][82]Another trial, this time using Navya vehicles, was run in 2019 from September to November.[83] |
| RDM Group "LUTZ Pathfinder" | In October 2017, RDM Group began a trial service with two seat vehicles between Trumpington Park and Ride andCambridge railway stationalong the guided busway, for possible use as an after hours service once the regular bus service has stopped each day.[84] |
| EasyMile "EZ10" | EasyMile has had longer term trials atWageningen UniversityandLausanneas well as short trials inDarwin,[85]Dubai,Helsinki,San Sebastián,Sophia Antipolis,Bordeaux[86]andTapei[87]In December 2017, a trial began inDenverrunning at5 miles per hour (8.0km/h)on a dedicated stretch of road.[88]EasyMile was operating in ten U.S. states, including California, Florida, Texas, Ohio, Utah, and Virginia before U.S. service was suspended after a February 2020 injury.[89]In August 2020 EasyMile was operating shuttles in 16 cities across the United States, includingSalt Lake City, Columbus, Ohio, and Corpus Christi, Texas.[90]In October 2020 a new trial was launched in Fairfax, Virginia.[91]In August 2021 a one-year trial was launched at the Colorado School of Mines in Golden, Colorado. The trial uses nine vehicles (with seven active at any time) and provides a 5–10 minute service along three routes at a maximum speed of12mph (19km/h). At the time of launch this was the largest such trial in the United States.[92][93]In November 2021, EasyMile became the first driverless solutions provider in Europe authorized to operate at Level 4 in mixed traffic, on a public road. "EZ10" has been making test runs on a medical campus in the southwestern city of Toulouse since March.[94][95] |
| Westfield Autonomous Vehicles "POD" | In 2017 and 2018, using a modified version of theUltraPRTcalled "POD", four vehicles were used as part of theGATEway projecttrial conducted inGreenwichin south London on a3.4 kilometres (2.1mi)route.[96]A number of other trials have been conducted in Birmingham, Manchester, Lake District National Park, University of the West of England and Filton Airfield.[97] |
| Next Future Transportation "pods" inDubai | In February 2018, the ten passenger (six seated),12 miles per hour (19km/h), autonomous pods which are capable of joining to form a bus, were demonstrated at theWorld Government Summitin Dubai. The demonstration was a collaboration with between Next-Future and Dubai's Roads and Transport Authority and the vehicles are under consideration for deployment there.[98] |
| "Apolong/Apollo" | In July 2018, a driverless eight seater shuttle bus was trialed at the 2018Shanghaiexpo after tests in Xiamen and Chongqing cities as part of Project Apollo, a mass-produced autonomous vehicle project launched by a consortium includingBaidu.[99][100][101] |
| Jacksonville Transportation Authority | Since December 2018, theJacksonville Transportation Authorityhas been using a 'test and learn' site at theFlorida State College at Jacksonville[102]to evaluate vehicles from different vendors as part of its plan for the Ultimate Urban Circulator (U2C). Among the six vehicles tested[103]are the Local Motors "Olli 2.0",[104]Navya "Autonom"[105]andEasyMile "EZ10".[106] |
| 2getthere "ParkShuttle" inBrussels | In 2019, trials were held at Brussels Airport[107]and atNanyang Technological Universityin Singapore.[108] |
| Ohmio "Lift" inChristchurch | In 2019, Trials with their 15-person shuttle were conducted inNew ZealandatChristchurch Airport[109]and at theChristchurch Botanic Gardens[110]in 2020. |
| Yutong"Xioayu" | Testing with the first generation vehicle in 2019 at theBoao Forum for Asiaand inZhengzhou.[111]The 10-seat second generation vehicle has been delivered to Guangzhou, Nanjing, Zhengzhou, Sansha, Changsha with public trials due to commence in July 2021 inZhengzhou.[68][112] |
| ARTC"WinBus" inChanghua city | In July 2020, a trial service began inChanghuacity in Taiwan, connecting four tourism factories inChanghua Coastal Industrial Parkalong a7.5km (4.7mi), with plans to extend the route to12.6km (7.8mi)to serve tourist destinations.[113]In January 2021, Level 4 "WinBus" got a license for one-year experimental sandbox operation.[114] |
| Yamaha Motor"Land Car" based "ZEN drive Pilot" inEiheiji town,Fukui prefecture, Japan | In December 2020,Eiheiji townstarted test operation of driverless autonomous driving mobility services by making use of a remotely-operated autonomous driving system.[115]AISTHuman-Centered Mobility Research Center modified Yamaha Motor's electric "Land Car" and the tracing road of an abandoned Eiheiji railway line. This system was legally approved as Level 3.[116]In March 2023, "ZEN drive Pilot" became the first legally approved Level 4 Automatic operation device under the amended "Road Traffic Act" of 2023.[117] |
| WeRide "Mini Robobus" | In January 2021, WeRide began testing its Mini Robobus onGuangzhou International Bio Island.[118]In June 2021, the company also launched trials at Nanjing. |
| Toyota "e-Palette"inChūō, Tokyo | During the2021 Tokyo Summer Olympics, a fleet of 20 vehicles was used to ferry athletes and others around the Athletes' Village. Each vehicle could carry 20 people or 4 wheelchairs and had a top speed of20mph (32km/h).[119](The event also used 200 driver operated variants called the"Accessible People Movers (APM)", to take athletes to their events.) On August 27, 2021, Toyota suspended all "e-Pallete" services at the Paralympics after a vehicle collided with and injured a visually impaired pedestrian,[120]and restarted on August 31 with improved safety measures.[121] |
| Hino "Poncho Long"tuned by Nippon Mobility inShinjuku, Tokyo | In November 2021,Tokyo Metropolitan Governmentstarted three trials. As one of the three, a lead contractorKeio Dentetsu Buswas planned to operate in the central area of themegalopolis.[122] |

 

*Vehicle names are in quotes*

 

### Buses

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/d/df/Stagecoach_autonomous_E200_MMC_trial.jpg/250px-Stagecoach_autonomous_E200_MMC_trial.jpg)](./File:Stagecoach_autonomous_E200_MMC_trial.jpg)The United Kingdom's first autonomous bus, currently on trial with [Stagecoach Manchester](./Stagecoach_Manchester) 

Autonomous buses are proposed, as well as self-driving cars and trucks. Grade 2 level automated minibusses were trialed for a few weeks in Stockholm.[[123]](./Vehicular_automation#cite_note-123)[[124]](./Vehicular_automation#cite_note-124) China has a small fleet of self-driving public buses in the tech district of Shenzhen, Guangdong.[[125]](./Vehicular_automation#cite_note-125)

 

The first autonomous bus trial in the United Kingdom commenced in mid-2019, with an [Alexander Dennis Enviro200 MMC](./Alexander_Dennis_Enviro200_MMC) single-decker bus modified with autonomous software from [Fusion Processing](./Fusion_Processing?action=edit&redlink=1) able to operate in driverless mode within [Stagecoach Manchester](./Stagecoach_Manchester)'s [Sharston](./Sharston) bus depot, performing tasks such as driving to the washing station, refueling point and then parking at a dedicated parking space in the depot.[[126]](./Vehicular_automation#cite_note-126) Passenger-carrying driverless bus trials in Scotland commenced in January 2023, with a fleet of five identical vehicles to the Manchester trial used on a 14 miles (23 km) [Stagecoach Fife](./Stagecoach_Fife) park-and-ride route across the [Forth Road Bridge](./Forth_Road_Bridge), from the north bank of the Forth to [Edinburgh Park station](./Edinburgh_Park_station).[[127]](./Vehicular_automation#cite_note-127)[[128]](./Vehicular_automation#cite_note-128)

 

Another autonomous trial in [Oxfordshire](./Oxfordshire), England, which uses a [battery electric](./Battery_electric_bus) [Fiat Ducato](./Fiat_Ducato) minibus on a circular service to [Milton Park](./Milton_Park), operated by [FirstBus](./FirstBus) with support from Fusion Processing, [Oxfordshire County Council](./Oxfordshire_County_Council) and the [University of the West of England](./University_of_the_West_of_England), entered full passenger service also in January 2023. The trial route will be extended to [Didcot Parkway railway station](./Didcot_Parkway_railway_station) after acquiring a larger single-decker by the end of 2023.[[129]](./Vehicular_automation#cite_note-129)[[130]](./Vehicular_automation#cite_note-130)

 

In July 2020 in Japan, [AIST](./National_Institute_of_Advanced_Industrial_Science_and_Technology) Human-Centered Mobility Research Center with Nippon Koei and [Isuzu](./Isuzu) started a series of demonstration tests for mid-sized buses, [Isuzu "Erga Mio"](./Isuzu_Erga_Mio) with autonomous driving systems, in five areas; [Ōtsu](./Ōtsu) city in [Shiga prefecture](./Shiga_prefecture), [Sanda](./Sanda,_Hyōgo) city in [Hyōgo Prefecture](./Hyōgo_Prefecture) and other three areas in sequence.[[131]](./Vehicular_automation#cite_note-131)[[132]](./Vehicular_automation#cite_note-132)[[133]](./Vehicular_automation#cite_note-FOOTNOTEShin_Kato20213–4-133)

 

In October 2023, [Imagry](./Imagry), an Israeli AI startup, introduced its mapless autonomous driving solution at Busworld Europe, leveraging a real-time image recognition system and a spatial deep convolutional neural network (DCNN) to mimic human driving behavior.[[134]](./Vehicular_automation#cite_note-134)

 

In September 2025, trade publications described the "smartbus" concept in connection with depot-based autonomous bus operation for manoeuvres such as parking, washing, and charging, in coverage of Autonomous Systems. The concept was presented at Busworld Europe later that year. In December 2025, a smartbus pilot involving the public transport operator PKM Gliwice in Poland was reported.[[135]](./Vehicular_automation#cite_note-Smartbus-135)[[136]](./Vehicular_automation#cite_note-SmartbusGliwice-136)

 

#### Modular autonomous transit

 

Modular autonomous transit is a research concept for public transit using self-driving vehicles with connectable units, or "pods", that can adjust capacity based on passenger demand.[[137]](./Vehicular_automation#cite_note-Chen-137) Studies suggest these systems could improve efficiency through dynamic routing, with simulations showing reduced travel times in urban networks, though no operational systems existed as of 2025.[[138]](./Vehicular_automation#cite_note-Wu-138)

 

### Trucks

 Further information: [Self-driving truck](./Self-driving_truck) 

The concept for autonomous vehicles has been applied for commercial uses, such as autonomous or nearly [autonomous trucks](./Autonomous_trucks).

 

Companies such as [Suncor Energy](./Suncor_Energy), a Canadian energy company, and [Rio Tinto Group](./Rio_Tinto_Group) were among the first to replace human-operated trucks with driverless commercial trucks run by computers.[[139]](./Vehicular_automation#cite_note-139) In April 2016, trucks from major manufacturers including [Volvo](./Volvo) and the [Daimler Company](./Daimler_Company) completed a week of autonomous driving across Europe, organized by the Dutch, in an effort to get self-driving trucks on the road. With developments in self-driving trucks progressing, U.S. self-driving truck sales is expected to reach 60,000 by 2035 according to a report released by [IHS Incorporated](./IHS_Inc.) in June 2016.[[140]](./Vehicular_automation#cite_note-140)

 

As reported in June 1995 in *[Popular Science](./Popular_Science)* magazine, self-driving trucks were being developed for combat convoys, whereby only the lead truck would be driven by a human and the following trucks would rely on satellite, an [inertial guidance](./Inertial_guidance) system and ground-speed sensors.[[141]](./Vehicular_automation#cite_note-PopularScienceJune1995-141) [Caterpillar Incorporated](./Caterpillar_Inc.) made early developments in 2013 with the [Robotics Institute](./Robotics_Institute) at [Carnegie Mellon University](./Carnegie_Mellon_University) to improve efficiency and reduce cost at various mining and construction sites.[[142]](./Vehicular_automation#cite_note-Gingrich2014-142)

 

In Europe, the [Safe Road Trains for the Environment](./Safe_Road_Trains_for_the_Environment) is such an approach.

 

From PWC's Strategy & Report,[[143]](./Vehicular_automation#cite_note-143) self driving trucks will be the source of concern around how this technology will impact around 3 million truck drivers in the US, as well as 4 million employees in support of the trucking economy in gas stations, restaurants, bars and hotels. At the same time, some companies like Starsky, are aiming for Level 3 Autonomy, which would see the driver playing a control role around the truck's environment. The company's project, remote truck driving, would give truck drivers a greater work-life balance, enabling them to avoid long periods away from their home. This would however provoke a potential mismatch between the driver's skills with the technological redefinition of the job.

 

Companies that buy driverless trucks could massively cut costs: human drivers would no longer be required, companies' liabilities due to truck accidents would diminish, and productivity would increase (as the driverless truck doesn't need to rest). The usage of self driving trucks will go hand in hand with the use of real-time data to optimize both efficiency and productivity of the service delivered, as a way to tackle traffic congestion for example. Driverless trucks could enable new business models that would see deliveries shift from day time to night time or time slots in which traffic is less heavily dense.

 

#### Suppliers

 
| Company | Details |
| --- | --- |
| Waymo Semi | In March 2018,Waymo, the automated vehicle company spun off fromGoogleparent companyAlphabet Incorporated, announced it was applying its technology to semi trucks. In the announcement, Waymo noted it would be using automated trucks to move freight related to Google's data centers in theAtlanta, Georgia area. The trucks will be manned and operated on public roads.[144] |
| Uber Semi | In October 2016,Ubercompleted the first driverless operation of an automated truck on public roads, delivering a trailer ofBudweiserbeer from Fort Collins, Colorado to Colorado Springs.[145]The run was completed at night on Interstate 25 after extensive testing and system improvements in cooperation with the Colorado State Police. The truck had a human in the cab but not sitting in the driver's seat, while the Colorado State Police provided a rolling closure of the highway.[146]At the time, Uber's automated truck was based primarily on technology developed byOtto, which Uber acquired in August 2016.[147]In March 2018, Uber announced it was using its automated trucks to deliver freight in Arizona, while also leveraging the UberFreight app to find and dispatch loads.[148] |
| Embark Semi | In February 2018, Embark Trucks announced it had completed the first cross-country trip of an automated semi, driving 2,400 miles from Los Angeles, California to Jacksonville, Florida on Interstate 10.[149]This followed a November 2017 announcement that it had partnered withElectroluxandRyderto test its automated truck by movingFrigidairerefrigerators from El Paso, Texas to Palm Springs, California.[150] |
| Tesla Semi | In November 2017Tesla, Incorporated, owned byElon Musk, revealed a prototype of theTesla Semiand announced that it would go into production. This long-haul, electric semi-truck can drive itself and move in "platoons" that automatically follow a lead vehicle. It was disclosed in August 2017 that it sought permission to test the vehicles inNevada.[151] |
| Starsky Robotics | In 2017,Starsky Roboticsunveiled its technology that allows to make trucks autonomous. Unlike its bigger competitors in this industry that aims to tackle Level 4 and 5 Autonomy, Starsky Robotics is aiming at producing Level 3 Autonomy trucks, in which the human drivers should be prepared to respond to a "request to intervene" in case anything goes wrong. |
| Pronto AI | In December 2018,Anthony Levandowskiunveiled his new autonomous driving company, Pronto, which is building L2 ADAS technology for the commercial trucking industry. The company is based in San Francisco, California.[152] |

 

### Motorcycles

 

Several self-balancing autonomous motorcycles were demonstrated in 2017 and 2018 from BMW, Honda and Yamaha.[[153]](./Vehicular_automation#cite_note-:12-153)[[154]](./Vehicular_automation#cite_note-154)[[155]](./Vehicular_automation#cite_note-155)

 
|  | This list isincomplete; you can help byadding missing items.(June 2021) |
| --- | --- |

  Suggest to add more headers to the table below, such as date, name of trial (if any), geographic location, and sort each entry by time/location.  
| Company/Location | Details |
| --- | --- |
| Honda motorcycle | Inspired by the Uni-cub, Honda implemented a self-balancing technology into their motorcycles. Due to the weight of motorcycles, it is often a challenge for motorcycle owners to keep balance of their vehicles at low speeds or at a stop. Honda's motorcycle concept has a self-balancing feature that will keep the vehicle upright. It automatically lowers the center of balance by extending the wheelbase. It then takes control of the steering to keep the vehicle balanced. This allows users to navigate the vehicle more easily when walking or driving in stop and go traffic. However, this system is not for high speed driving.[153][156] |
| BMWs Motorrad Vision concept motorcycle | BMW Motorrad developed the ConnectRide self driving motorcycle in order to push the boundaries of motorcycle safety. The autonomous features of the motorcycle include emergency braking, negotiating intersections, assisting during tight turns, and front impact avoidance. These are features similar to current technologies that are being developed and implemented in autonomous cars. This motorcycle can also fully drive on its own at normal driving speed, making turns and returning to a designated location. It lacks the self standing feature that Honda has implemented.[157] |
| Yamaha's riderless motorcycle | "Motoroid" can hold its balance, autonomously driving, recognizing riders and go to a designated location with a hand gesture. Yamaha used the "Human beings react a hell of a lot quicker" research philosophy into the motoroid. The idea is that the autonomous vehicle is not attempting to replace human beings, but to augment the abilities of the human with advanced technology. They have tactile feedback such as a gentle squeeze to a rider's lower back as a reassuring caress at dangerous speeds, as if the vehicle was responding and communicating with the rider. Their goal is to "meld" the machine and human together to form one experience.[158] |
| Harley-Davidson | While their motorcycles are popular, one of the largest problems of owning a Harley-Davidson is the reliability of the vehicle. It is difficult to manage the weight of the vehicle at low speeds and picking it up from the ground can be a difficult process even with correct techniques. In order to attract more customers, they filed a patent for having a gyroscope at the back of the vehicle that will keep the balance of the motorcycle for the rider at low speeds. After 3 miles per hour, the system disengages. However anything below that, the gyroscope can handle the balance of the vehicle which means it can balance even at a stop. This system can be removed if the rider feels ready without it (meaning it is modular).[156] |

 

### Trains

 Main article: [Automatic train operation](./Automatic_train_operation) 

The concept for autonomous vehicles has also been applied for commercial uses, like for autonomous trains. The world's first driverless urban transit system is the [Port Island Line](./Port_Island_Line) in [Kobe](./Kobe), Japan, opened in 1981.[[159]](./Vehicular_automation#cite_note-DIAMOND_Online-159) The first self-driving train in the UK was launched in London on the Thameslink route.[[160]](./Vehicular_automation#cite_note-160)

 

An example of an automated train network is the [Docklands Light Railway](./Docklands_Light_Railway) in [London](./London).

 

Also see [List of automated train systems](./List_of_automated_train_systems).

 

### Trams

 

In 2018 the first autonomous [trams in Potsdam](./Trams_in_Potsdam) were trialed.[[161]](./Vehicular_automation#cite_note-161)

 

### Automated guided vehicle

 Main article: [Automated guided vehicle](./Automated_guided_vehicle) 

An automated guided vehicle or automatic guided vehicle (AGV) is a mobile robot that follows markers or wires in the floor, or uses vision, magnets, or lasers for navigation. They are most often used in industrial applications to move materials around a manufacturing facility or warehouse. Application of the automatic guided vehicle had broadened during the late 20th century.

 

## Aircraft

 Main article: [Unmanned aerial vehicle](./Unmanned_aerial_vehicle) 

Aircraft have received much attention for automation, especially for navigation. A system capable of autonomously navigating a vehicle (especially aircraft) is known as [autopilot](./Autopilot).

 

### Delivery drones

 Main article: [Delivery drone](./Delivery_drone) 

Various industries such as packages and food have experimented with delivery drones. Traditional and new transportation companies are competing in the market. For example, [UPS Flight Forward](./UPS_Flight_Forward), Alphabet Wing, and [Amazon Prime Air](./Amazon_Prime_Air) are all developing delivery drones.[[162]](./Vehicular_automation#cite_note-:13-162) [Zipline](./Zipline_(drone_delivery)), an American medical drone delivery company, has the largest active drone delivery operations in the world, and its drones are capable of Level 4 autonomy.[[163]](./Vehicular_automation#cite_note-163)

 

However, even if technology seems to allow for those solutions to function correctly as various tests of various companies show, the main throwback to the market launch and use of such drones is inevitably the legislation in place and regulatory agencies have to decide on the framework they wish to take to draft regulation. This process is in different phases across the world as each country will tackle the topic independently. For example, Iceland's government and departments of transport, aviation, police have already started issuing licenses for drone operations. It has a permissive approach and together with Costa Rica, Italy, the UAE, Sweden and Norway, has a fairly unrestricted legislation on commercial drone use. Those countries are characterized by a body of regulation that may give operational guidelines or require licensing, registration and insurance.[[164]](./Vehicular_automation#cite_note-164)

 

On the other side, other countries have decided to ban, either directly (outright ban) or indirectly (effective ban), the use of commercial drones. The RAND Corporation thus notes the difference between countries forbidding drones and those that have a formal process for commercial drone licensing, but requirements are either impossible to meet or licenses do not appear to have been approved. In the US, United Parcel Service is the only delivery service with the Part 135 Standard certification that is required to use drones to deliver to real customers.[[162]](./Vehicular_automation#cite_note-:13-162)

 

However, most countries seem to be struggling on the integration of drones for commercial uses into their aviation regulatory frameworks. Thus, constraints are placed on the use of those drones such as that they must be operating within the visual line of sight (VLOS) of the pilot and thus limiting their potential range. This would be the case of the Netherlands and Belgium. Most countries let pilots operate outside the VLOS but is subject to restrictions and pilot ratings, which would be the case of the US.

 

The general trend is that legislation is moving fast and laws are constantly being reevaluated. Countries are moving towards a more permissive approach but the industry still lacks infrastructures to ensure the success of such a transition. To provide safety and efficiency, specialized training courses, pilot exams (type of UAV and flying conditions) as well as liability management measures regarding insurances may need to be developed.

 

There is a sense of urgency related to this innovation as competition is high and companies lobby to integrate them rapidly in their products and services offerings. Since June 2017, the US Senate legislation reauthorized the Federal Aviation Administration and the Department of Transportation to create a carrier certificate allowing for package deliveries by drones.[[165]](./Vehicular_automation#cite_note-165)

 

## Watercraft

 Main article: [Unmanned surface vehicle](./Unmanned_surface_vehicle) 

Autonomous boats can provide security, perform research, or conduct hazardous or repetitive tasks (such as guiding a large ship into a harbor or transporting cargo).

 

### DARPA

 

[Sea Hunter](./Sea_Hunter) is an [autonomous](./Autonomous) [unmanned surface vehicle](./Unmanned_surface_vehicle) (USV) launched in 2016 as part of the [DARPA](./DARPA) [Anti-Submarine Warfare](./Anti-Submarine_Warfare) Continuous Trail Unmanned Vessel ([ACTUV](./ACTUV)) program.

 

## Submersibles

 Main article: [Autonomous underwater vehicle](./Autonomous_underwater_vehicle) 

Underwater vehicles have been a focus for automation for tasks such as pipeline inspection and underwater mapping.

 

## Assistance robots

 

### Spot

 

This four-legged robot was created to be able to navigate through many different terrain outdoors and indoors. It can walk on its own without colliding into anything. It uses many different sensors, including 360-degree vision cameras and gyroscopes. It is able to keep its balance even when pushed over. This vehicle, while it is not intended to be ridden, can carry heavy loads for construction workers or military personnel through rough terrain.[[166]](./Vehicular_automation#cite_note-166)

 

## Regulation

 See also: [Regulation of self-driving cars](./Regulation_of_self-driving_cars) 

The British [Highway Code](./The_Highway_Code) states that: 

 

By **self-driving vehicles**, we mean those listed as automated vehicles by the Secretary of State for Transport under the Automated and Electric Vehicles Act 2018.

— The Highway Code – 27/07/2022, p. 4

 

The UK considers the way to update its British Highway Code for automated code:

 

Automated vehicles can perform all the tasks involved in driving, in at least some situations. They differ from vehicles fitted with assisted driving features (like [cruise control](./Cruise_control) and [lane-keeping assistance](./Lane_departure_warning_system)), which carry out some tasks, but where the driver is still responsible for driving. If you are driving a vehicle with assisted driving features, you MUST stay in control of the vehicle.

— proposed changes to The Highway Code[[167]](./Vehicular_automation#cite_note-gov.uk-167)

 

If the vehicle is designed to require you to resume driving after being prompted to, while the vehicle is driving itself, you MUST remain in a position to be able to take control. For example, you should not move out of the driving seat. You should not be so distracted that you cannot take back control when prompted by the vehicle.

— proposed changes to The Highway Code[[167]](./Vehicular_automation#cite_note-gov.uk-167)

 

## Concerns

 

### Lack of control

 

Through the autonomy level, it is shown that the higher the level of autonomy, the less control humans have on their vehicles (highest level of autonomy needing zero human interventions). One concerns regarding the development of vehicular automation is related to the end-users' trust in the technology that controls automated vehicles.[[168]](./Vehicular_automation#cite_note-:0-168) According to a nationally conducted survey made by [Kelley Blue Book](./Kelley_Blue_Book) (KBB) in 2016, it was shown that the majority of people would choose to have a certain level of control behind their own vehicle rather than having the vehicle operate in Level 5 autonomy, or in other words, complete autonomy.[[169]](./Vehicular_automation#cite_note-:1-169) According to half of the respondents, the idea of safety in an autonomous vehicle diminishes as the level of autonomy increases.[[169]](./Vehicular_automation#cite_note-:1-169) This distrust of autonomous driving systems proved to be unchanged throughout the years when a nationwide survey conducted by [AAA Foundation for Traffic and Safety](./AAA_Foundation_for_Traffic_Safety) (AAAFTS) in 2019 showed the same outcome as the survey KBB did in 2016. AAAFTS survey showed that even though people have a certain level of trust in automated vehicles, most people also have doubts and distrust towards the technology used in autonomous vehicles, with most distrust in Level 5 autonomous vehicles.[[170]](./Vehicular_automation#cite_note-:2-170) It is shown by AAAFTS' survey that people's trust in autonomous driving systems increased when their level of understanding increased.[[170]](./Vehicular_automation#cite_note-:2-170)

 

### Malfunctions

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/42/Uber_autonomous_vehicle_prototype_testing_in_San_Francisco.jpg/330px-Uber_autonomous_vehicle_prototype_testing_in_San_Francisco.jpg)](./File:Uber_autonomous_vehicle_prototype_testing_in_San_Francisco.jpg)A prototype of an autonomous Uber car being tested in San Francisco, California 

The possibility of autonomous vehicle's technology to experience malfunctions is also one of the causes of user's distrust in autonomous driving systems.[[168]](./Vehicular_automation#cite_note-:0-168) It is the concern that most respondents voted for in the AAAFTS survey.[[170]](./Vehicular_automation#cite_note-:2-170) Even though autonomous vehicles are made to improve traffic safety by minimizing crashes and their severity,[[170]](./Vehicular_automation#cite_note-:2-170) they still caused fatalities. At least 113 autonomous vehicle related accidents have occurred until 2018.[[171]](./Vehicular_automation#cite_note-171) In 2015, Google declared that their automated vehicles experienced at least 272 failures, and drivers had to intervene around 13 times to prevent fatalities.[[172]](./Vehicular_automation#cite_note-:3-172) Furthermore, other automated vehicles' manufacturers also reported automated vehicles' failures, including the Uber car incident.[[172]](./Vehicular_automation#cite_note-:3-172) A self-driving Uber car accident in 2018 is an example of autonomous vehicle accidents that are also listed among self-driving car fatalities. A report made by the [National Transportation Safety Board](./National_Transportation_Safety_Board) (NTSB) showed that the self-driving Uber car was unable to identify the victim in a sufficient amount of time for the vehicle to slow down and avoid crashing into the victim.[[173]](./Vehicular_automation#cite_note-173)

 

### Ethical

 

Another concern related to vehicle automation is its ethical issues. In reality, autonomous vehicles can encounter inevitable traffic accidents. In such situations, many risks and calculations need to be made in order to minimize the amount of damage the accident could cause.[[174]](./Vehicular_automation#cite_note-:4-174) When a human driver encounters an inevitable accident, the driver will take a spontaneous action based on ethical and moral logic. However, when a driver has no control over the vehicle (Level 5 autonomy), the system of an autonomous vehicle needs to make that quick decision.[[174]](./Vehicular_automation#cite_note-:4-174) Unlike humans, autonomous vehicles can only make decisions based on what it is programmed to do.[[174]](./Vehicular_automation#cite_note-:4-174) However, the situation and circumstances of accidents differ from one another, and any one decision might not be the best decision for certain accidents. Based on two research studies in 2019,[[175]](./Vehicular_automation#cite_note-:5-175)[[176]](./Vehicular_automation#cite_note-:6-176) the implementation of fully automated vehicles in traffic where semi-automated and non-automated vehicles are still present might lead to complications.[[175]](./Vehicular_automation#cite_note-:5-175) Some flaws that still need consideration include the structure of liability, distribution of responsibilities,[[176]](./Vehicular_automation#cite_note-:6-176) efficiency in decision making, and the performance of autonomous vehicles with its diverse surroundings.[[175]](./Vehicular_automation#cite_note-:5-175) Still, researchers [Steven Umbrello](./Steven_Umbrello?action=edit&redlink=1) and [Roman V. Yampolskiy](./Roman_Yampolskiy) propose that the [value sensitive design](./Value_sensitive_design) approach is one method that can be used to design autonomous vehicles to avoid some of these ethical issues and design for human values.[[177]](./Vehicular_automation#cite_note-177)

 

## See also

 
- [Self-driving car](./Self-driving_car)
- [Self-driving truck](./Self-driving_truck)
- [Dashcam](./Dashcam)
- [Intelligent speed adaptation](./Intelligent_speed_adaptation)
- [Intelligent Transportation System](./Intelligent_Transportation_System)
- [Robotaxi](./Robotaxi)
- [Transit media](./Transit_media)
- [Uncrewed vehicle](./Uncrewed_vehicle)
- [Software Defined Vehicle](./Software_Defined_Vehicle) (SDV)

 

## References

  
1. [↑](./Vehicular_automation#cite_ref-1) ["Self-steering Mars Rover tested at ESO's Paranal Observatory"](http://www.eso.org/public/announcements/ann12048/). *ESO Announcement*. Retrieved 21 June 2012.
2. [↑](./Vehicular_automation#cite_ref-tvt2_2-0) Hu, Junyan; Bhowmick, Parijat; Lanzon, Alexander (August 2021). ["Group Coordinated Control of Networked Mobile Robots With Applications to Object Transportation"](https://doi.org/10.1109%2FTVT.2021.3093157). *IEEE Transactions on Vehicular Technology*. **70** (8): 8269–8274. [Bibcode](./Bibcode_(identifier)):[2021ITVT...70.8269H](https://ui.adsabs.harvard.edu/abs/2021ITVT...70.8269H). [doi](./Doi_(identifier)):[10.1109/TVT.2021.3093157](https://doi.org/10.1109%2FTVT.2021.3093157). [ISSN](./ISSN_(identifier)) [0018-9545](https://search.worldcat.org/issn/0018-9545).
3. [1](./Vehicular_automation#cite_ref-tro_3-0) [2](./Vehicular_automation#cite_ref-tro_3-1) Hu, Junyan; Bhowmick, Parijat; Jang, Inmo; Arvin, Farshad; Lanzon, Alexander (December 2021). "A Decentralized Cluster Formation Containment Framework for Multirobot Systems". *IEEE Transactions on Robotics*. **37** (6): 1936–1955. [Bibcode](./Bibcode_(identifier)):[2021ITRob..37.1936H](https://ui.adsabs.harvard.edu/abs/2021ITRob..37.1936H). [doi](./Doi_(identifier)):[10.1109/TRO.2021.3071615](https://doi.org/10.1109%2FTRO.2021.3071615). [ISSN](./ISSN_(identifier)) [1552-3098](https://search.worldcat.org/issn/1552-3098).
4. [↑](./Vehicular_automation#cite_ref-4) Chan, Ching-Yao (2017). ["Advancements, prospects, and impacts of automated driving systems"](https://doi.org/10.1016%2Fj.ijtst.2017.07.008). *International Journal of Transportation Science and Technology*. **6** (3): 208–216. [doi](./Doi_(identifier)):[10.1016/j.ijtst.2017.07.008](https://doi.org/10.1016%2Fj.ijtst.2017.07.008).
5. [↑](./Vehicular_automation#cite_ref-5) Zhao, Jingyuan; Zhao, Wenyi; Deng, Bo; Wang, Zhenghong; Zhang, Feng; Zheng, Wenxiang; Cao, Wanke; Nan, Jinrui; Lian, Yubo; Burke, Andrew F. (2024). "Autonomous driving system: A comprehensive survey". *Expert Systems with Applications*. **242** 122836. [doi](./Doi_(identifier)):[10.1016/j.eswa.2023.122836](https://doi.org/10.1016%2Fj.eswa.2023.122836).
6. [↑](./Vehicular_automation#cite_ref-6) Martínez-Díaz, Margarita; Soriguera, Francesc (2018). ["Autonomous vehicles: theoretical and practical challenges"](https://doi.org/10.1016%2Fj.trpro.2018.10.103). *Transportation Research Procedia*. **33**: 275–282. [doi](./Doi_(identifier)):[10.1016/j.trpro.2018.10.103](https://doi.org/10.1016%2Fj.trpro.2018.10.103). [hdl](./Hdl_(identifier)):[2183/21640](https://hdl.handle.net/2183%2F21640).
7. [↑](./Vehicular_automation#cite_ref-7) Fisher, Donald L. (2020). *Handbook of Human Factors for Automated, Connected, and Intelligent Vehicles*. William J. Horrey, John D. Lee, Michael A. Regan. Milton: Taylor & Francis Group. [ISBN](./ISBN_(identifier)) [978-1-351-97980-1](./Special:BookSources/978-1-351-97980-1).
8. [↑](./Vehicular_automation#cite_ref-tcas_8-0) Hu, Junyan; Turgut, Ali Emre; Lennox, Barry; Arvin, Farshad (January 2022). ["Robust Formation Coordination of Robot Swarms With Nonlinear Dynamics and Unknown Disturbances: Design and Experiments"](https://durham-repository.worktribe.com/output/1205426). *IEEE Transactions on Circuits and Systems II: Express Briefs*. **69** (1): 114–118. [Bibcode](./Bibcode_(identifier)):[2022ITCSE..69..114H](https://ui.adsabs.harvard.edu/abs/2022ITCSE..69..114H). [doi](./Doi_(identifier)):[10.1109/TCSII.2021.3074705](https://doi.org/10.1109%2FTCSII.2021.3074705). [ISSN](./ISSN_(identifier)) [1549-7747](https://search.worldcat.org/issn/1549-7747).
9. [↑](./Vehicular_automation#cite_ref-9) ["Automated Vehicles for Safety | NHTSA"](https://web.archive.org/web/20211007021013/https://www.nhtsa.gov/technology-innovation/automated-vehicles-safety). *www.nhtsa.gov*. Archived from [the original](https://www.nhtsa.gov/technology-innovation/automated-vehicles-safety) on 7 October 2021. Retrieved 21 November 2021.
10. [1](./Vehicular_automation#cite_ref-Self-driving_car_SAE_definitions2_10-0) [2](./Vehicular_automation#cite_ref-Self-driving_car_SAE_definitions2_10-1) ["Automated Driving – Levels of Driving Automation are Defined in New SAE International Standard J3016"](https://web.archive.org/web/20180701034327/https://cdn.oemoffhighway.com/files/base/acbm/ooh/document/2016/03/automated_driving.pdf) (PDF). *[SAE International](./SAE_International)*. 2014. Archived from [the original](https://cdn.oemoffhighway.com/files/base/acbm/ooh/document/2016/03/automated_driving.pdf) (PDF) on 1 July 2018.
11. [↑](./Vehicular_automation#cite_ref-11) ([Badue et al. 2021](./Vehicular_automation#CITEREFBadue_et_al.2021), p. 1)
12. [1](./Vehicular_automation#cite_ref-auto_12-0) [2](./Vehicular_automation#cite_ref-auto_12-1) ([Azam et al. 2020](./Vehicular_automation#CITEREFAzam_et_al.2020), p. 6)
13. [↑](./Vehicular_automation#cite_ref-13) ([Serban et al. 2020](./Vehicular_automation#CITEREFSerban_et_al.2020), p. 23)
14. [↑](./Vehicular_automation#cite_ref-14) ([Badue et al. 2021](./Vehicular_automation#CITEREFBadue_et_al.2021), p. 2)
15. [↑](./Vehicular_automation#cite_ref-15) Charroud, Anas; El Moutaouakil, Karim; Palade, Vasile; Yahyaouy, Ali; Onyekpe, Uche; Eyo, Eyo U. (7 February 2024). ["Localization and Mapping for Self-Driving Vehicles: A Survey"](https://doi.org/10.3390%2Fmachines12020118). *Machines*. **12** (2): 6. [doi](./Doi_(identifier)):[10.3390/machines12020118](https://doi.org/10.3390%2Fmachines12020118).
16. [↑](./Vehicular_automation#cite_ref-16) ([Serban et al. 2020](./Vehicular_automation#CITEREFSerban_et_al.2020), p. 26)
17. [1](./Vehicular_automation#cite_ref-:8_17-0) [2](./Vehicular_automation#cite_ref-:8_17-1) Adnan, Nadia; Md Nordin, Shahrina; bin Bahruddin, Mohamad Ariff; Ali, Murad (December 2018). "How trust can drive forward the user acceptance to the technology? In-vehicle technology for autonomous vehicle". *Transportation Research Part A: Policy and Practice*. **118**: 819–836. [Bibcode](./Bibcode_(identifier)):[2018TRPA..118..819A](https://ui.adsabs.harvard.edu/abs/2018TRPA..118..819A). [doi](./Doi_(identifier)):[10.1016/j.tra.2018.10.019](https://doi.org/10.1016%2Fj.tra.2018.10.019). [S2CID](./S2CID_(identifier)) [158645252](https://api.semanticscholar.org/CorpusID:158645252).
18. [↑](./Vehicular_automation#cite_ref-18) Gupta, Abhishek; Anpalagan, Alagan; Guan, Ling; Khwaja, Ahmed Shaharyar (July 2021). ["Deep learning for object detection and scene perception in self-driving cars: Survey, challenges, and open issues"](https://doi.org/10.1016%2Fj.array.2021.100057). *Array*. **10** 100057. [Elsevier](./Elsevier). [doi](./Doi_(identifier)):[10.1016/j.array.2021.100057](https://doi.org/10.1016%2Fj.array.2021.100057).
19. [↑](./Vehicular_automation#cite_ref-19) Kuutti, Sampo; Bowden, Richard; Jin, Yaochu; Barber, Phil; Fallah, Saber (February 2021). "A Survey of Deep Learning Applications to Autonomous Vehicle Control". *IEEE Transactions on Intelligent Transportation Systems*. **22** (2). [Institute of Electrical and Electronics Engineers](./Institute_of_Electrical_and_Electronics_Engineers): 712–733. [arXiv](./ArXiv_(identifier)):[1912.10773](https://arxiv.org/abs/1912.10773). [Bibcode](./Bibcode_(identifier)):[2021ITITr..22..712K](https://ui.adsabs.harvard.edu/abs/2021ITITr..22..712K). [doi](./Doi_(identifier)):[10.1109/TITS.2019.2962338](https://doi.org/10.1109%2FTITS.2019.2962338).
20. [↑](./Vehicular_automation#cite_ref-20) Yeong, De Jong; Velasco-Hernandez, Gustavo; Barry, John; Walsh, Joseph (18 March 2021). ["Sensor and Sensor Fusion Technology in Autonomous Vehicles: A Review"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8003231). *[Sensors](./Sensors_(journal))*. **21** (6): 2140. [Bibcode](./Bibcode_(identifier)):[2021Senso..21.2140Y](https://ui.adsabs.harvard.edu/abs/2021Senso..21.2140Y). [doi](./Doi_(identifier)):[10.3390/s21062140](https://doi.org/10.3390%2Fs21062140). [PMC](./PMC_(identifier)) [8003231](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8003231). [PMID](./PMID_(identifier)) [33803889](https://pubmed.ncbi.nlm.nih.gov/33803889).
21. [↑](./Vehicular_automation#cite_ref-21) ([Serban et al. 2020](./Vehicular_automation#CITEREFSerban_et_al.2020), p. 25)
22. [1](./Vehicular_automation#cite_ref-:9_22-0) [2](./Vehicular_automation#cite_ref-:9_22-1) Van Brummelen, Jessica; O'Brien, Marie; Gruyer, Dominique; Najjaran, Homayoun (April 2018). "Autonomous vehicle perception: The technology of today and tomorrow". *Transportation Research Part C: Emerging Technologies*. **89**: 384–406. [Bibcode](./Bibcode_(identifier)):[2018TRPC...89..384V](https://ui.adsabs.harvard.edu/abs/2018TRPC...89..384V). [doi](./Doi_(identifier)):[10.1016/j.trc.2018.02.012](https://doi.org/10.1016%2Fj.trc.2018.02.012).
23. [↑](./Vehicular_automation#cite_ref-23) Song, Haina; Zhou, Shengpei; Chang, Zhenting; Su, Yuejiang; Liu, Xiaosong; Yang, Jingfeng (1 January 2021). ["Collaborative processing and data optimization of environmental perception technologies for autonomous vehicles"](https://www.emerald.com/insight/content/doi/10.1108/aa-01-2021-0007/full/html). *Assembly Automation*. **41** (3): 283–291. [doi](./Doi_(identifier)):[10.1108/AA-01-2021-0007](https://doi.org/10.1108%2FAA-01-2021-0007). [ISSN](./ISSN_(identifier)) [0144-5154](https://search.worldcat.org/issn/0144-5154).
24. [↑](./Vehicular_automation#cite_ref-24) ["HD Maps vs AV Maps – The Crucial Differences"](https://www.mobileye.com/blog/av-maps-vs-hd-maps/). *Mobileye*. 28 February 2021.
25. [↑](./Vehicular_automation#cite_ref-:11_25-0) Wigley, Edward; Rose, Gillian (2 April 2020). ["Who's behind the wheel? Visioning the future users and urban contexts of connected and autonomous vehicle technologies"](http://oro.open.ac.uk/70471/1/2020_FINAL_Who_s_behind_the_wheel.pdf) (PDF). *Geografiska Annaler: Series B, Human Geography*. **102** (2): 155–171. [doi](./Doi_(identifier)):[10.1080/04353684.2020.1747943](https://doi.org/10.1080%2F04353684.2020.1747943). [S2CID](./S2CID_(identifier)) [219087578](https://api.semanticscholar.org/CorpusID:219087578).
26. [↑](./Vehicular_automation#cite_ref-26) ["Developments in Modern GNSS and Its Impact on Autonomous Vehicle Architectures"](https://www.swiftnav.com/resource/white-paper/developments-in-modern-gnss-and-its-impact-on-autonomous-vehicle-0). *www.swiftnav.com*. December 2020. Retrieved 11 June 2025.
27. [↑](./Vehicular_automation#cite_ref-27) Wilks, Yorik (2019). *Artificial Intelligence: Modern Magic or Dangerous Future?*. London, England. pp. 3–4. [ISBN](./ISBN_(identifier)) [9781785-78-516-0](./Special:BookSources/9781785-78-516-0).`{{cite book}}`:  CS1 maint: location missing publisher ([link](./Category:CS1_maint:_location_missing_publisher))
28. [↑](./Vehicular_automation#cite_ref-28) ["Watson"](http://watson.latech.edu/book/intelligence/intelligenceOverview5b4.html). *watson.latech.edu*. Retrieved 9 December 2025.
29. [↑](./Vehicular_automation#cite_ref-29) Pomerleau, Dean A. ["ALVINN: AN AUTONOMOUS LAND VEHICLE IN A NEURAL NETWORK"](https://papers.neurips.cc/paper_files/paper/1988/file/812b4ba287f5ee0bc9d43bbf5bbe87fb-Paper.pdf) (PDF). *papers.neurips.cc*. Pittsburgh, PA: Computer Science Department, Carnegie Mellon University. Retrieved 8 December 2025.
30. [↑](./Vehicular_automation#cite_ref-30) EPRS Automated vehicles in the EU, Members' Research Service Page 2 of 12, Glossary [https://www.europarl.europa.eu/RegData/etudes/BRIE/2016/573902/EPRS_BRI(2016)573902_EN.pdf](https://www.europarl.europa.eu/RegData/etudes/BRIE/2016/573902/EPRS_BRI(2016)573902_EN.pdf)
31. [↑](./Vehicular_automation#cite_ref-31) Cruz, Roberto (18 February 2019). ["AAA Studies Technology Behind Self-Driving Cars"](https://web.archive.org/web/20210620042034/https://magazine.northeast.aaa.com/daily/life/technology/aaa-studies-technology-behind-self-driving-cars/). *Your AAA Network*. Archived from [the original](https://magazine.northeast.aaa.com/daily/life/technology/aaa-studies-technology-behind-self-driving-cars/) on 20 June 2021. Retrieved 21 February 2020.
32. [↑](./Vehicular_automation#cite_ref-32) ["The SARTRE project"](https://web.archive.org/web/20101127172612/http://www.sartre-project.eu/en/Sidor/default.aspx). Archived from [the original](http://www.sartre-project.eu/en/Sidor/default.aspx) on 27 November 2010.
33. [↑](./Vehicular_automation#cite_ref-33) Marshall, Aarian. ["After a Deadly Crash, Uber Returns Robocars to the Road"](https://www.wired.com/story/uber-returns-self-driving-after-deadly-crash/). *Wired*. [ISSN](./ISSN_(identifier)) [1059-1028](https://search.worldcat.org/issn/1059-1028). Retrieved 5 May 2023.
34. [↑](./Vehicular_automation#cite_ref-34) ["Uber Self-Driving Cars Hit The Streets Of Pittsburgh"](https://www.cbsnews.com/pittsburgh/news/uber-driverless-cars-hit-the-streets-of-pittsburgh/). *www.cbsnews.com*. 14 September 2016. Retrieved 5 May 2023.
35. [↑](./Vehicular_automation#cite_ref-35) ["California's first driverless bus hits the road in San Ramon"](https://abc7news.com/san-ramon-driverless-bus-test-testing-autonomous/3183813/). *ABC7 San Francisco*. 7 March 2018. Retrieved 5 May 2023.
36. [↑](./Vehicular_automation#cite_ref-computer_world_36-0) Mearian, Lucas (19 August 2016). ["Ford remains wary of Tesla-like autonomous driving features"](http://web.archive.org/web/20160820074538/http://www.computerworld.com/article/3109217/car-tech/ford-wary-of-tesla-like-autonomous-driving-features.html). *Computer World*. Archived from [the original](http://www.computerworld.com/article/3109217/car-tech/ford-wary-of-tesla-like-autonomous-driving-features.html) on 20 August 2016. Retrieved 9 December 2016.
37. [1](./Vehicular_automation#cite_ref-Automated_Vehicle_Technology_2014_37-0) [2](./Vehicular_automation#cite_ref-Automated_Vehicle_Technology_2014_37-1) "Automated Vehicle Technology." King Coal Highway 292 (2014): 23-29.
38. [1](./Vehicular_automation#cite_ref-Tesla_Loss_38-0) [2](./Vehicular_automation#cite_ref-Tesla_Loss_38-1) ["A Tragic Loss"](https://www.tesla.com/blog/tragic-loss). *Tesla*. 30 June 2016. Retrieved 10 December 2016.
39. [↑](./Vehicular_automation#cite_ref-39) Hallerbach, Sven; Xia, Yiqun; Eberle, Ulrich; Koester, Frank (3 April 2018). "Simulation-Based Identification of Critical Scenarios for Cooperative and Automated Vehicles". *SAE International Journal of Connected and Automated Vehicles*. **1** (2): 93–106. [doi](./Doi_(identifier)):[10.4271/2018-01-1066](https://doi.org/10.4271%2F2018-01-1066).
40. [↑](./Vehicular_automation#cite_ref-:7_40-0) Yigitcanlar; Wilson; Kamruzzaman (24 April 2019). ["Disruptive Impacts of Automated Driving Systems on the Built Environment and Land Use: An Urban Planner's Perspective"](https://doi.org/10.3390%2Fjoitmc5020024). *Journal of Open Innovation: Technology, Market, and Complexity*. **5** (2): 24. [doi](./Doi_(identifier)):[10.3390/joitmc5020024](https://doi.org/10.3390%2Fjoitmc5020024). [hdl](./Hdl_(identifier)):[10419/241315](https://hdl.handle.net/10419%2F241315).
41. [1](./Vehicular_automation#cite_ref-:15_41-0) [2](./Vehicular_automation#cite_ref-:15_41-1) [3](./Vehicular_automation#cite_ref-:15_41-2) Anderson, Mark (May 2020). "The road ahead for self-driving cars: The AV industry has had to reset expectations, as it shifts its focus to level 4 autonomy – [News]". *IEEE Spectrum*. **57** (5): 8–9. [Bibcode](./Bibcode_(identifier)):[2020IEEES..57e...8A](https://ui.adsabs.harvard.edu/abs/2020IEEES..57e...8A). [doi](./Doi_(identifier)):[10.1109/MSPEC.2020.9078402](https://doi.org/10.1109%2FMSPEC.2020.9078402). [S2CID](./S2CID_(identifier)) [219070930](https://api.semanticscholar.org/CorpusID:219070930).
42. [1](./Vehicular_automation#cite_ref-:16_42-0) [2](./Vehicular_automation#cite_ref-:16_42-1) [3](./Vehicular_automation#cite_ref-:16_42-2) Campbell, Mark; Egerstedt, Magnus; How, Jonathan P.; Murray, Richard M. (13 October 2010). "Autonomous driving in urban environments: approaches, lessons and challenges". *Philosophical Transactions of the Royal Society A: Mathematical, Physical and Engineering Sciences*. **368** (1928): 4649–4672. [Bibcode](./Bibcode_(identifier)):[2010RSPTA.368.4649C](https://ui.adsabs.harvard.edu/abs/2010RSPTA.368.4649C). [doi](./Doi_(identifier)):[10.1098/rsta.2010.0110](https://doi.org/10.1098%2Frsta.2010.0110). [PMID](./PMID_(identifier)) [20819826](https://pubmed.ncbi.nlm.nih.gov/20819826). [S2CID](./S2CID_(identifier)) [17558587](https://api.semanticscholar.org/CorpusID:17558587).
43. [1](./Vehicular_automation#cite_ref-:17_43-0) [2](./Vehicular_automation#cite_ref-:17_43-1) [3](./Vehicular_automation#cite_ref-:17_43-2) [4](./Vehicular_automation#cite_ref-:17_43-3) [5](./Vehicular_automation#cite_ref-:17_43-4) Panagiotopoulos, Ilias; Dimitrakopoulos, George (October 2018). "An empirical investigation on consumers' intentions towards autonomous driving". *Transportation Research Part C: Emerging Technologies*. **95**: 773–784. [Bibcode](./Bibcode_(identifier)):[2018TRPC...95..773P](https://ui.adsabs.harvard.edu/abs/2018TRPC...95..773P). [doi](./Doi_(identifier)):[10.1016/j.trc.2018.08.013](https://doi.org/10.1016%2Fj.trc.2018.08.013). [S2CID](./S2CID_(identifier)) [117555199](https://api.semanticscholar.org/CorpusID:117555199).
44. [↑](./Vehicular_automation#cite_ref-44) Shladover, Steven E.; Nowakowski, Christopher (April 2019). "Regulatory challenges for road vehicle automation: Lessons from the California experience". *Transportation Research Part A: Policy and Practice*. **122**: 125–133. [Bibcode](./Bibcode_(identifier)):[2019TRPA..122..125S](https://ui.adsabs.harvard.edu/abs/2019TRPA..122..125S). [doi](./Doi_(identifier)):[10.1016/j.tra.2017.10.006](https://doi.org/10.1016%2Fj.tra.2017.10.006). [S2CID](./S2CID_(identifier)) [113811906](https://api.semanticscholar.org/CorpusID:113811906).
45. [↑](./Vehicular_automation#cite_ref-45) Hancock, P. A.; Kajaks, Tara; Caird, Jeff K.; Chignell, Mark H.; Mizobuchi, Sachi; Burns, Peter C.; Feng, Jing; Fernie, Geoff R.; Lavallière, Martin; Noy, Ian Y.; Redelmeier, Donald A.; Vrkljan, Brenda H. (5 February 2020). ["Challenges to Human Drivers in Increasingly Automated Vehicles"](https://doi.org/10.1177/0018720819900402). *Human Factors: The Journal of the Human Factors and Ergonomics Society*. **62** (2): 310–328. [doi](./Doi_(identifier)):[10.1177/0018720819900402](https://doi.org/10.1177%2F0018720819900402). [ISSN](./ISSN_(identifier)) [0018-7208](https://search.worldcat.org/issn/0018-7208).
46. [↑](./Vehicular_automation#cite_ref-46) Umar Zakir Abdul, Hamid; et al. (2021). ["Adopting Aviation Safety Knowledge into the Discussions of Safe Implementation of Connected and Autonomous Road Vehicles"](https://www.researchgate.net/publication/350669647). *SAE Technical Papers (SAE WCX Digital Summit)* (2021–01–0074). Retrieved 12 April 2021.
47. [↑](./Vehicular_automation#cite_ref-47) ["Amendment proposal to the 1968 Convention on Road Traffic"](https://unece.org/fileadmin/DAM/trans/doc/2020/wp1/ECE-TRANS-WP1-2020-1e.pdf) (PDF). Economic Commission for Europe. March 2020. Retrieved 13 November 2021.
48. [↑](./Vehicular_automation#cite_ref-48) ["Explanatory memorandum: Proposal of Amendment to Article 1 and new Article 34 BIS of the 1968 Convention on Road Traffic"](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/1023594/EM_MS_5.2021_Proposal_Amendment_1968_Convention_Road_Traffic.odt).
49. [1](./Vehicular_automation#cite_ref-ReferenceA_49-0) [2](./Vehicular_automation#cite_ref-ReferenceA_49-1) SMMT publishes guiding principles for marketing automated vehicles, SMMT, 22 November 2021
50. [↑](./Vehicular_automation#cite_ref-50) ["Driverless robot buses crash"](http://www.wolfstad.com/2005/12/driveless-robot-busses-crash/). Wolfstad.com. 6 December 2005. Retrieved 20 November 2011.
51. [↑](./Vehicular_automation#cite_ref-51) ["Driverless robot buses crash, Part 2"](http://www.wolfstad.com/2005/12/driverless-robot-buses-crash-part-2/). Wolfstad.com. 17 December 2005. Retrieved 20 November 2011.
52. [↑](./Vehicular_automation#cite_ref-52) ["S&P Global Homepage | S&P Global"](http://auto.ihs.com/news/eu-en-intelligent-cars-faq.htm).
53. [↑](./Vehicular_automation#cite_ref-53) ["Vauxhall Vectra | Auto Express News | News"](http://www.autoexpress.co.uk/news/autoexpressnews/62349/vauxhall_vectra.html). *Auto Express*. 29 November 2005. Retrieved 20 November 2011.
54. [↑](./Vehicular_automation#cite_ref-54) ["Nissan | News Press Release"](https://web.archive.org/web/20111027124358/http://www.nissan-global.com/EN/NEWS/2006/_STORY/060315-01-e.html). Nissan-global.com. 15 March 2006. Archived from [the original](http://www.nissan-global.com/EN/NEWS/2006/_STORY/060315-01-e.html) on 27 October 2011. Retrieved 20 November 2011.
55. [↑](./Vehicular_automation#cite_ref-55) ["Singapore's driverless vehicle ambitions reach next milestone with new national standards"](https://web.archive.org/web/20190202212227/https://www.channelnewsasia.com/news/technology/singapore-driverless-vehicle-autonomous-national-standards-11190498). *Channel NewsAsia*. Archived from [the original](https://www.channelnewsasia.com/news/technology/singapore-driverless-vehicle-autonomous-national-standards-11190498) on 2 February 2019. Retrieved 2 February 2019.
56. [↑](./Vehicular_automation#cite_ref-56) ["EU SUSTAINABLE ENERGY WEEK 18-22 JUNE 2012"](https://cms.esi.info/Media/documents/683049_1339586615722.pdf) (PDF). p. 14. Retrieved 21 June 2021.
57. [↑](./Vehicular_automation#cite_ref-57) ["Final Report Summary – CITYMOBIL2 (Cities demonstrating cybernetic mobility)"](https://cordis.europa.eu/project/id/314190/reporting). 11 November 2016. Retrieved 17 August 2021.
58. [↑](./Vehicular_automation#cite_ref-58) ["Experiments on autonomous and automated driving: an overview 2015"](https://web.archive.org/web/20220604015734/https://www.anwb.nl/binaries/content/assets/anwb/pdf/over-anwb/persdienst/rapport_inventarisatie_zelfrijdende_auto.pdf) (PDF). Archived from [the original](https://www.anwb.nl/binaries/content/assets/anwb/pdf/over-anwb/persdienst/rapport_inventarisatie_zelfrijdende_auto.pdf) (PDF) on 4 June 2022. Retrieved 28 June 2021.
59. [↑](./Vehicular_automation#cite_ref-59) Kitchen, Sebastian (8 December 2016). ["JTA recommends replacing Skyway with driverless vehicles, creating corridor from Riverside to EverBank Field"](http://jacksonville.com/news/2016-12-08/jta-recommends-replacing-skyway-driverless-vehicles-creating-corridor-riverside). *Florida Times-Union*. Retrieved 25 January 2017.
60. [↑](./Vehicular_automation#cite_ref-60) ["JTA Board Chair Embraces Autonomous Vehicles To Replace Skyway"](https://news.wjct.org/post/jta-board-chair-embraces-autonomous-vehicles-replace-skyway). 15 April 2021. Retrieved 10 June 2021.
61. [↑](./Vehicular_automation#cite_ref-61) ["Introducing the world's first completely unattended public autonomous vehicle"](https://www.eurotransportmagazine.com/22257/news/industry-news/worlds-first-unattended-autonomous-vehicle/). *Euro Transport Magazine*. 20 February 2017. Retrieved 1 September 2017.
62. [↑](./Vehicular_automation#cite_ref-62) ["Rivium 3rd generation"](https://www.2getthere.eu/projects/rivium/rivium-3-0/). 12 August 2020. Retrieved 10 June 2021.
63. [↑](./Vehicular_automation#cite_ref-63) ["Baidu just made its 100th autonomous bus ahead of commercial launch in China"](https://techcrunch.com/2018/07/03/baidu-just-made-its-100th-autonomous-bus-ahead-of-commercial-launch-in-china/). Tech Crunch. 4 July 2018. Retrieved 14 July 2021.
64. [↑](./Vehicular_automation#cite_ref-64) ["Top 25 autonomous shuttle manufacturers"](https://roboticsandautomationnews.com/2020/10/15/top-25-autonomous-shuttle-manufacturers/37291/). 15 October 2020.
65. [↑](./Vehicular_automation#cite_ref-65) ["Toyota Unveils Their e-Palette Self-Driving Shuttles"](https://www.ubergizmo.com/2020/12/toyota-e-palette-self-driving-shuttle/). Retrieved 28 June 2021.
66. [↑](./Vehicular_automation#cite_ref-66) ["Toyota e-Palette autonomous vehicles to be rolled out "within the next few years""](https://www.caradvice.com.au/923460/toyota-e-palette-autonomous-vehicles-to-be-rolled-out-within-the-next-few-years/). caradvice. 11 February 2021. Retrieved 28 June 2021.
67. [↑](./Vehicular_automation#cite_ref-67) ["China Autonomous Shuttle Market Report 2021 Featuring 10 Chinese Companies & 5 International Companies"](https://www.globenewswire.com/en/news-release/2021/04/21/2213924/28124/en/China-Autonomous-Shuttle-Market-Report-2021-Featuring-10-Chinese-Companies-5-International-Companies.html). 21 April 2021. Retrieved 28 June 2021.
68. [1](./Vehicular_automation#cite_ref-XiaoyuJune2021_68-0) [2](./Vehicular_automation#cite_ref-XiaoyuJune2021_68-1) ["Yutong has already delivered 100 autonomous micro-buses Xiaoyu 2.0 models to Zhengzhou"](https://www.youtube.com/watch?v=O4f8VUy5VjA). *[YouTube](./YouTube)*. 4 July 2021. [Archived](https://ghostarchive.org/varchive/youtube/20211214/O4f8VUy5VjA) from the original on 14 December 2021. Retrieved 14 July 2021.
69. [↑](./Vehicular_automation#cite_ref-69) ["Walkabout The World's Largest Bus Factory (Yutong Industrial Park)"](https://www.youtube.com/watch?v=PNXLXCV9nXA). *[YouTube](./YouTube)*. 7 July 2021. [Archived](https://ghostarchive.org/varchive/youtube/20211214/PNXLXCV9nXA) from the original on 14 December 2021. Retrieved 14 July 2021.
70. [↑](./Vehicular_automation#cite_ref-70) ["Hong Kong Airport's unmanned patrol cars"](https://www.passengerselfservice.com/2022/03/hong-kong-airport-now-has-4-unmanned-patrol-cars/). 16 March 2022.
71. [↑](./Vehicular_automation#cite_ref-71) ["Autonomous Shuttle Pilots in Europe, AMD Aspirations in Austin"](https://viodi.com/2021/06/02/autonomous-shuttle-pilots-in-europe-amd-aspirations-in-austin/). 3 June 2021. Retrieved 10 June 2021.
72. [↑](./Vehicular_automation#cite_ref-72) ["BESTMILE AND TRAPEZE JOIN FORCES TO BRING AUTONOMOUS MOBILITY TO CITIES ALL AROUND THE GLOBE"](https://motiondigest.com/2016/10/10/bestmile-and-trapeze-join-forces-to-bring-autonomous-mobility-to-cities-all-around-the-globe/). *Motion Digest Network*. 10 October 2016. Retrieved 1 December 2021.
73. [↑](./Vehicular_automation#cite_ref-73) ["Swiss move on with self-driving buses"](https://www.swissinfo.ch/eng/driverless-vehicles-autonomous-buses-switzerland/47001252). *swissinfo.ch*. 5 October 2021. Retrieved 1 December 2021.
74. [↑](./Vehicular_automation#cite_ref-74) ["Washington D.C. residents can ride in this adorable driverless shuttle starting this summer"](http://www.businessinsider.com/olli-driverless-shuttle-hits-dc-roads-2016-6?r=US&IR=T). *Business Insider*. 16 June 2016. Retrieved 5 October 2017.
75. [↑](./Vehicular_automation#cite_ref-75) [Autonomous shuttle Olli deployed in Turin, Italy](https://newmobility.global/autonomous/autonomous-shuttle-olli-deployed-turin-italy/) JAN 17, 2020
76. [↑](./Vehicular_automation#cite_ref-76) Scott, Mark (28 May 2017). ["The Future of European Transit: Driverless and Utilitarian"](https://www.nytimes.com/2017/05/28/technology/the-future-of-european-transit-driverless-and-utilitarian.html). *The New York Times*. Retrieved 8 September 2017.
77. [↑](./Vehicular_automation#cite_ref-77) ["Las Vegas launches driverless shuttle bus test run on public roads"](https://www.techrepublic.com/article/las-vegas-launches-driverless-shuttle-bus-test-run-on-public-roads/). 12 January 2017. Retrieved 1 September 2017.
78. [↑](./Vehicular_automation#cite_ref-78) ["Driverless bus takes to the road in Perth"](http://www.theaustralian.com.au/business/technology/driverless-bus-takes-to-the-road-in-perth/news-story/05b173c19c7474949df57927639586cb). *The Australian*. 1 September 2016. Retrieved 1 September 2017.
79. [↑](./Vehicular_automation#cite_ref-79) ["Navya driverless shuttles to begin ferrying University of Michigan students this fall"](https://techcrunch.com/2017/06/21/navya-driverless-shuttles-to-begin-ferrying-university-of-michigan-students-this-fall/). *Tech Crunch*. 21 June 2017. Retrieved 1 September 2017.
80. [↑](./Vehicular_automation#cite_ref-80) ["Experimentations with Navya's Autonomous Shuttles"](http://web.archive.org/web/20210628054706/https://navya.tech/en/experimentations-with-autonomous-shuttles/). *NAVYA*. Archived from [the original](https://navya.tech/en/experimentations-with-autonomous-shuttles/) on 28 June 2021. Retrieved 28 June 2021.
81. [↑](./Vehicular_automation#cite_ref-81) ["HITCHING A RIDE Project looks to bring autonomous shuttles to Texas A&M campus"](https://www.theeagle.com/news/local/project-looks-to-bring-autonomous-shuttles-to-texas-a-m/article_363998fa-27ab-5afb-9990-405134b0cbc3.html). *The Eagle*. 24 August 2017. Retrieved 5 September 2017.
82. [↑](./Vehicular_automation#cite_ref-82) ["Autonomous Shuttle"](https://unmanned.tamu.edu/projects/autonomous-shuttle/). *Unmanned Systems Lab Texas A&M University*. Retrieved 5 September 2017.
83. [↑](./Vehicular_automation#cite_ref-83) ["Catch A Ride On TTI's Autonomous Shuttle"](https://today.tamu.edu/2019/09/17/catch-a-ride-on-ttis-autonomous-shuttle/). 17 September 2019. Retrieved 28 June 2021.
84. [↑](./Vehicular_automation#cite_ref-84) ["Driverless robot 'pods' take to the Cambridge guided busway"](http://www.cambridge-news.co.uk/news/cambridge-news/driverless-robot-pods-take-cambridge-13772841). 18 October 2017. Retrieved 24 October 2017.
85. [↑](./Vehicular_automation#cite_ref-85) ["Driverless Bus TESTING ROUTE NOTICE"](https://web.archive.org/web/20170912102130/https://transport.nt.gov.au/transport/driverless-bus). Northern Territory Government. 5 September 2017. Archived from [the original](https://transport.nt.gov.au/transport/driverless-bus) on 12 September 2017. Retrieved 12 September 2017.
86. [↑](./Vehicular_automation#cite_ref-86) ["Easymile | Driverless shuttle for the last mile"](https://web.archive.org/web/20170901110650/http://easymile.com/projects/). *EasyMile*. Archived from [the original](http://easymile.com/projects/) on 1 September 2017. Retrieved 1 September 2017.
87. [↑](./Vehicular_automation#cite_ref-87) ["Society Driverless bus test in Taipei gets positive feedback"](http://focustaiwan.tw/news/asoc/201708050009.aspx). Focus Taiwan News Channel. 5 August 2017. Retrieved 1 September 2017.
88. [↑](./Vehicular_automation#cite_ref-88) ["Denver's first driverless shuttle hits the test track, avoids tumbleweed before possible 2018 launch"](http://www.denverpost.com/2017/12/04/denver-driverless-shuttle-test-easymile/). 4 December 2017. Retrieved 7 December 2017.
89. [↑](./Vehicular_automation#cite_ref-89) ["U.S. agency suspends self-driving shuttle EasyMile use in 10 U.S. states"](https://www.reuters.com/article/autos-selfdriving-idUSL1N2AP1FG). *Reuters*. 25 February 2020 – via www.reuters.com.
90. [↑](./Vehicular_automation#cite_ref-90) ["'This is our future': Fairfax tests region's first self-driving shuttle for public transit"](https://www.washingtonpost.com/local/trafficandcommuting/this-is-our-future-fairfax-tests-regions-first-self-driving-shuttle-for-public-transit/2020/08/16/c3e7a1ac-dca1-11ea-8051-d5f887d73381_story.html). 17 August 2020. Retrieved 28 June 2021.
91. [↑](./Vehicular_automation#cite_ref-91) ["Transdev partners with Fairfax County to launch connected AV pilot project"](https://www.masstransitmag.com/alt-mobility/autonomous-vehicles/press-release/21161672/transdev-north-america-transdev-partners-with-fairfax-county-to-launch-connected-av-pilot-project). 6 November 2020. Retrieved 28 June 2021.
92. [↑](./Vehicular_automation#cite_ref-92) ["Nation's largest fleet of autonomous, electric shuttles launches in Colorado"](https://www.masstransitmag.com/alt-mobility/autonomous-vehicles/press-release/21234137/autonomous-vehicles-colorado-avco-nations-largest-fleet-of-autonomous-electric-shuttles-launches-in-colorado). Mass Transit. 13 August 2021. Retrieved 13 August 2021.
93. [↑](./Vehicular_automation#cite_ref-93) ["The Mines Rover"](https://www.youtube.com/watch?v=0LmeMmw4ny4). *[YouTube](./YouTube)*. 10 August 2021. [Archived](https://ghostarchive.org/varchive/youtube/20211214/0LmeMmw4ny4) from the original on 14 December 2021. Retrieved 13 August 2021.
94. [↑](./Vehicular_automation#cite_ref-94) ["France approves fully autonomous bus for driving on public roads in a European first"](https://www.euronews.com/next/2021/12/01/france-approves-fully-autonomous-bus-for-driving-on-public-roads-in-a-european-first). *[Euronews](./Euronews)*. 2 December 2021. Retrieved 3 December 2021.
95. [↑](./Vehicular_automation#cite_ref-95) ["EasyMile First Authorized at Level 4 of Autonomous Driving on Public Roads"](http://web.archive.org/web/20211122202036/https://easymile.com/news/easymile-first-authorized-level-4-autonomous-driving-public-roads). *EasyMile* (Press release). 22 November 2021. Archived from [the original](https://easymile.com/news/easymile-first-authorized-level-4-autonomous-driving-public-roads) on 22 November 2021. Retrieved 3 December 2021.
96. [↑](./Vehicular_automation#cite_ref-96) ["GATEway Project"](https://trl.co.uk/projects/gateway-project/). Retrieved 28 June 2021.
97. [↑](./Vehicular_automation#cite_ref-97) ["Westfield Technology Group autonomous POD confirmed for Fleet Live 2019"](https://web.archive.org/web/20210628030728/https://www.fleetnews.co.uk/news/fleet-industry-news/2019/08/01/westfield-technology-group-autonomous-pod-confirmed-for-fleet-live-2019). 1 August 2019. Archived from [the original](https://www.fleetnews.co.uk/news/fleet-industry-news/2019/08/01/westfield-technology-group-autonomous-pod-confirmed-for-fleet-live-2019) on 28 June 2021. Retrieved 28 June 2021.
98. [↑](./Vehicular_automation#cite_ref-98) ["Dubai tests the world's first autonomous mobility pods"](https://inhabitat.com/dubai-tests-first-autonomous-mobility-pods-in-the-world/). 15 February 2018. Retrieved 25 February 2018.
99. [↑](./Vehicular_automation#cite_ref-99) ["Baidu apollo self driving cars"](https://www.businessinsider.com/microsoft-baidu-apollo-self-driving-cars-2017-7). *Business Insider*. 2 July 2017. Retrieved 12 November 2018.
100. [↑](./Vehicular_automation#cite_ref-100) ["Baidu starts mass production of autonomous buses"](https://www.dw.com/en/baidu-starts-mass-production-of-autonomous-buses/a-44525629). Deutche World. 5 July 2018. Retrieved 12 November 2018.
101. [↑](./Vehicular_automation#cite_ref-101) ["Baidu's Robin Li Reveals Unmanned Bus, AI Chip, Digital Assistant Upgrade at Tech Summit"](https://web.archive.org/web/20181112181652/https://www.yicaiglobal.com/news/baidus-robin-li-reveals-unmanned-bus-ai-chip-digital-assistant-upgrade-tech-summit). Yicai Global. 4 July 2018. Archived from [the original](https://www.yicaiglobal.com/news/baidus-robin-li-reveals-unmanned-bus-ai-chip-digital-assistant-upgrade-tech-summit) on 12 November 2018. Retrieved 12 November 2018.
102. [↑](./Vehicular_automation#cite_ref-102) ["JTA, FSCJ execute agreement for autonomous vehicle testing and educational initiatives"](https://www.masstransitmag.com/alt-mobility/autonomous-vehicles/press-release/21141133/jacksonville-transportation-authority-jta-jta-fscj-execute-agreement-for-autonomous-vehicle-testing-and-educational-initiatives). Mass Transit. 5 June 2020. Retrieved 28 June 2021.
103. [↑](./Vehicular_automation#cite_ref-103) ["JTA Receives 6th Autonomous U2C Program Test Vehicle; FSCJ Part Of Latest Test"](https://news.wjct.org/post/jta-receives-6th-autonomous-u2c-program-test-vehicle-fscj-part-latest-test). WJCT. 15 September 2020. Retrieved 28 June 2021.
104. [↑](./Vehicular_automation#cite_ref-104) ["Olli 2.0 joins JTA's U2C testing program"](https://www.jaxdailyrecord.com/article/olli-2-0-joins-jtas-u2c-testing-program). Jacksonville Daily Record. 16 September 2020. Retrieved 28 June 2021.
105. [↑](./Vehicular_automation#cite_ref-105) ["JTA testing ADA accessible autonomous vehicle"](https://www.masstransitmag.com/bus/paratransit/press-release/21113162/jacksonville-transportation-authority-jta-jta-testing-ada-accessible-autonomous-vehicle). Mass Transit. 5 November 2019. Retrieved 28 June 2021.
106. [↑](./Vehicular_automation#cite_ref-106) ["JTA Unveils U²C Gen-2 Test Vehicle"](https://web.archive.org/web/20210628094342/https://u2c.jtafla.com/media-center/news-press/jta-unveils-u-c-gen-2-test-vehicle/). Archived from [the original](https://u2c.jtafla.com/media-center/news-press/jta-unveils-u-c-gen-2-test-vehicle/) on 28 June 2021. Retrieved 28 June 2021.
107. [↑](./Vehicular_automation#cite_ref-107) ["Self-driving people mover makes its maiden trip at brussels airport"](https://www.2getthere.eu/news/maiden-trip-at-brussels-airport/). 13 May 2019. Retrieved 28 June 2021.
108. [↑](./Vehicular_automation#cite_ref-108) ["NTU Singapore to test autonomous vehicles on the NTU Smart Campus"](https://web.archive.org/web/20210628080320/https://www.eurekalert.org/pub_releases/2018-04/ntu-nst041618.php). Archived from [the original](https://www.eurekalert.org/pub_releases/2018-04/ntu-nst041618.php) on 28 June 2021. Retrieved 28 June 2021.
109. [↑](./Vehicular_automation#cite_ref-109) ["NEWS New Zealand's first autonomous shuttle debuts at Christchurch Airport"](https://www.internationalairportreview.com/news/95394/new-zealand-first-autonomous-shuttle/). Retrieved 28 June 2021.
110. [↑](./Vehicular_automation#cite_ref-110) ["Autonomous shuttle rides for Christchurch public to park the fear factor"](https://www.stuff.co.nz/motoring/119563299/autonomous-shuttle-rides-for-christchurch-public-to-park-the-fear-factor). 16 February 2020. Retrieved 28 June 2021.
111. [↑](./Vehicular_automation#cite_ref-111) ["Yutong 5G-Enabled Intelligent Mobility Solution Live Show"](https://en.yutong.com/technology/autonomous-driving/). Retrieved 14 July 2021.
112. [↑](./Vehicular_automation#cite_ref-112) ["Riding an Autonomous Bus ON THE CITY STREETS in China (Xiaoyu 2.0)"](https://www.youtube.com/watch?v=zu0373D6cPk). *[YouTube](./YouTube)*. 2 July 2021. [Archived](https://ghostarchive.org/varchive/youtube/20211214/zu0373D6cPk) from the original on 14 December 2021. Retrieved 14 July 2021.
113. [↑](./Vehicular_automation#cite_ref-113) ["Taiwan's first autonomous minibus begins operations in Changhua"](https://taiwantoday.tw/news.php?unit=6&post=181407). Taiwan Today. 16 July 2020. Retrieved 27 November 2021.
114. [↑](./Vehicular_automation#cite_ref-114) ["First Homegrown Autonomous Shuttle Wins Operating License in Taiwan"](https://web.archive.org/web/20211127031349/https://www.autofutures.tv/2021/01/11/first-homegrown-autonomous-shuttle-wins-operating-license-in-taiwan/). Auto Future. 11 January 2021. Archived from [the original](https://www.autofutures.tv/2021/01/11/first-homegrown-autonomous-shuttle-wins-operating-license-in-taiwan/) on 27 November 2021. Retrieved 27 November 2021.
115. [↑](./Vehicular_automation#cite_ref-115) ["Test Operation of Remote Controlled Driverless Autonomous Driving Mobility Services to Start"](https://www.meti.go.jp/english/press/2020/1211_005.html). *[METI, Japan](./Ministry_of_Economy,_Trade_and_Industry)*. 11 December 2020. Retrieved 23 November 2021.
116. [↑](./Vehicular_automation#cite_ref-116) Shin Kato (November 2021). ["AIST's efforts toward social implementation of automated driving mobility services"](https://en.sip-adus.go.jp/evt/workshop2021/file/sbi/SBI_HF_5E_Shin_Kato.pdf) (PDF). *SIP-adus*. pp. 5–13. Retrieved 23 November 2021.
117. [↑](./Vehicular_automation#cite_ref-117) ["国内初！自動運転車に対するレベル4の認可を取得しました"](https://www.meti.go.jp/press/2022/03/20230331002/20230331002.html) [Domestically the first! Approved as Level 4 self-driving car]. *[METI, Japan](./Ministry_of_Economy,_Trade_and_Industry)*. 31 March 2023. Retrieved 3 April 2023.
118. [↑](./Vehicular_automation#cite_ref-118) ["Chinese autonomous driving startup WeRide launches Mini Robobus in Guangzhou"](http://autonews.gasgoo.com/icv/70017949.html). 29 January 2021. Retrieved 28 June 2021.
119. [↑](./Vehicular_automation#cite_ref-119) ["Covid Won't Stop The Olympics Nor Toyota's Autonomous EV Transportation For Athletes"](https://www.forbes.com/sites/peterlyon/2021/06/30/covid-wont-stop-the-olympics-nor-toyotas-autonomous-ev-transportation-for-athletes/?sh=7ab9ec91d147). *Forbes*. 30 June 2021. Retrieved 13 August 2021.
120. [↑](./Vehicular_automation#cite_ref-120) ["Toyota halts all self-driving e-Palette vehicles after Olympic village accident"](https://www.reuters.com/business/autos-transportation/toyota-halts-all-self-driving-e-pallete-vehicles-after-olympic-village-accident-2021-08-27/). Reuters. 28 August 2021. Retrieved 29 August 2021.
121. [↑](./Vehicular_automation#cite_ref-121) ["Toyota self-driving buses in Paralympic village to restart on Aug. 31"](https://english.kyodonews.net/news/2021/08/f57b83f9f778-breaking-news-toyota-self-driving-buses-in-paralympic-village-to-restart-tues.html). *[Kyodo News](./Kyodo_News)*. 30 August 2021. Retrieved 17 November 2021.
122. [↑](./Vehicular_automation#cite_ref-122) ["【東京の西新宿と臨海副都心で自動運転移動サービスへ 都が実証実験の実施を決定"](https://response.jp/article/2021/07/19/347800.html) [Tokyo Metropolitan Government decided to conduct trials on autonomous mobility services in west-Shinjyuku area and bay-front area]. *Response* (in Japanese). 19 July 2021. Retrieved 2 December 2021.
123. [↑](./Vehicular_automation#cite_ref-123) ["Self-driving shuttle buses hit the streets of Stockholm"](https://newatlas.com/ericsson-self-driving-buses/53126/). New Atlas. 25 January 2018.
124. [↑](./Vehicular_automation#cite_ref-124) ["Smart Mobility is here"](https://www.youtube.com/watch?v=-NlZJxznXMo) – via www.youtube.com.
125. [↑](./Vehicular_automation#cite_ref-125) ["Self-driving buses are being tested in China and they're the largest of their kind yet"](https://mashable.com/2017/12/04/self-driving-bus-china/#Sq91uPlCJOq8). Mashable. 4 December 2017.
126. [↑](./Vehicular_automation#cite_ref-126) ["UK's first driverless bus trialled in Manchester"](https://www.independent.co.uk/life-style/driverless-bus-stagecoach-trial-manchester-technology-sensors-a8829741.html). *[Independent.co.uk](./Independent.co.uk)*. 19 March 2019. [Archived](https://ghostarchive.org/archive/20220811/https://www.independent.co.uk/life-style/driverless-bus-stagecoach-trial-manchester-technology-sensors-a8829741.html) from the original on 11 August 2022.
127. [↑](./Vehicular_automation#cite_ref-127) ["First driverless Edinburgh to Fife bus trial announced"](https://www.bbc.co.uk/news/uk-scotland-edinburgh-east-fife-46309121). *BBC News*. 22 November 2018.
128. [↑](./Vehicular_automation#cite_ref-128) Peat, Chris (23 January 2023). ["First passengers board Stagecoach autonomous bus"](https://www.busandcoachbuyer.com/first-passengers-board-stagecoach-autonomous-bus/). *Bus & Coach Buyer*. Retrieved 24 January 2023.
129. [↑](./Vehicular_automation#cite_ref-129) Peat, Chris (23 January 2023). ["Autonomous bus starts trials in Oxfordshire"](https://www.busandcoachbuyer.com/autonomous-bus-starts-trials-in-oxfordshire/). *Bus & Coach Buyer*. Retrieved 24 January 2023.
130. [↑](./Vehicular_automation#cite_ref-130) ["UK's first self-driving electric bus unveiled"](https://www.oxfordmail.co.uk/news/national/23269912.uks-first-self-driving-electric-bus-unveiled/). *Oxford Mail*. 23 January 2023. Retrieved 23 January 2023.
131. [↑](./Vehicular_automation#cite_ref-131) ["Public Road Demonstration Tests of Mid-Sized Buses with Autonomous Driving Systems to be Launched"](https://www.meti.go.jp/english/press/2020/0710_004.html). *[METI, Japan](./Ministry_of_Economy,_Trade_and_Industry)*. 10 July 2020. Retrieved 20 November 2021.
132. [↑](./Vehicular_automation#cite_ref-132) ["The Isuzu Group Value Creation Story: Growth Strategies"](https://www.isuzu.co.jp/world/company/investor/financial/pdf/annual21e_05.pdf) (PDF). *[Isuzu](./Isuzu)*. 10 July 2020. p. 26. Retrieved 20 November 2021.
133. [↑](./Vehicular_automation#cite_ref-FOOTNOTEShin_Kato20213–4_133-0) [Shin Kato 2021](./Vehicular_automation#CITEREFShin_Kato2021), pp. 3–4.
134. [↑](./Vehicular_automation#cite_ref-134) Hübner, Irina. ["Neuronale Netze und selbstlernende KI: Mapless-Autonomous-Fahrlösung für Busse"](https://www.elektroniknet.de/automotive/assistenzsysteme/mapless-autonomous-fahrloesung-fuer-busse.210186.html). *Elektroniknet* (in German). Retrieved 31 January 2024.
135. [↑](./Vehicular_automation#cite_ref-Smartbus_135-0) ["Autonomous Systems introduces Smartbus: because autonomous driving starts in the depot"](https://www.sustainable-bus.com/news/autonomous-systems-smartbus-autonomous-driving-depot/). *Sustainable Bus*. 16 September 2025.
136. [↑](./Vehicular_automation#cite_ref-SmartbusGliwice_136-0) ["Smartbus pilot kicks off: Autonomous Systems and PKM Gliwice test depot autonomous driving"](https://www.sustainable-bus.com/autonomous-driving/smartbus-pilot-autonomous-systems-pkm-gliwice-test-depot-autonomous-driving/). *Sustainable Bus*. December 2025.
137. [↑](./Vehicular_automation#cite_ref-Chen_137-0) Tian, Qingyun; Lin, Yun H.; Wang, David Z.; Liu, Yang (2022). "Planning for modular-vehicle transit service system: Model formulation and solution methods". *Transportation Research Part C: Emerging Technologies*. **138** 103627. [Bibcode](./Bibcode_(identifier)):[2022TRPC..13803627T](https://ui.adsabs.harvard.edu/abs/2022TRPC..13803627T). [doi](./Doi_(identifier)):[10.1016/j.trc.2022.103627](https://doi.org/10.1016%2Fj.trc.2022.103627).
138. [↑](./Vehicular_automation#cite_ref-Wu_138-0) Wu, Jiaming; Kulcsár, Balázs; Qu, Xiaobo (2021). ["A modular, adaptive, and autonomous transit system (MAATS): An in-motion transfer strategy and performance evaluation in urban grid transit networks"](https://doi.org/10.1016%2Fj.tra.2021.07.005). *Transportation Research Part A: Policy and Practice*. **151**: 81–98. [Bibcode](./Bibcode_(identifier)):[2021TRPA..151...81W](https://ui.adsabs.harvard.edu/abs/2021TRPA..151...81W). [doi](./Doi_(identifier)):[10.1016/j.tra.2021.07.005](https://doi.org/10.1016%2Fj.tra.2021.07.005).
139. [↑](./Vehicular_automation#cite_ref-139) ["Suncor Seeks Cost Cutting With Robot Trucks in Oil-Sands Mine"](https://www.bloomberg.com/news/articles/2013-10-31/suncor-seeks-cost-cutting-with-robot-trucks-in-oil-sands-mine). *Bloomberg-.com*. 13 October 2013. Retrieved 14 June 2016.
140. [↑](./Vehicular_automation#cite_ref-140) ["HS Clarifies Autonomous Vehicle Sales Forecast – Expects 21 Million Sales Globally in the Year 2035 and Nearly 76 Million Sold Globally Through 2035"](http://press.ihs.com/press-release/automotive/autonomous-vehicle-sales-set-reach-21-million-globally-2035-ihs-says). ihs-.com. 9 June 2016. Retrieved 14 June 2016.
141. [↑](./Vehicular_automation#cite_ref-PopularScienceJune1995_141-0) Nelson, Ray (June 1995). ["Leave The Driving To Us"](https://books.google.com/books?id=KrfIjdl-EMwC&pg=PA26). *Popular Science*. p. 26.
142. [↑](./Vehicular_automation#cite_ref-Gingrich2014_142-0) Gingrich, Newt (7 October 2014). [*Breakout: Pioneers of the Future, Prison Guards of the Past, and the Epic Battle That Will Decide America's Fate*](https://books.google.com/books?id=1SAjBQAAQBAJ&pg=PA14). Regnery Publishing. p. 114. [ISBN](./ISBN_(identifier)) [978-1-62157-281-7](./Special:BookSources/978-1-62157-281-7).
143. [↑](./Vehicular_automation#cite_ref-143) ["Transportation invests for a new future"](https://www.strategyand.pwc.com/gx/en/insights/archive/transportation-invests-future/transportation-invests-for-a-new-future.pdf) (PDF). *www.strategyand.pwc.com*.
144. [↑](./Vehicular_automation#cite_ref-144) ["Waymo's self-driving trucks will start delivering freight in Atlanta"](https://www.theverge.com/2018/3/9/17100518/waymo-self-driving-truck-google-atlanta). *The Verge*. Retrieved 13 March 2018.
145. [↑](./Vehicular_automation#cite_ref-145) ["Uber's Self-Driving Truck Makes Its First Delivery: 50,000 Budweisers"](https://www.wired.com/2016/10/ubers-self-driving-truck-makes-first-delivery-50000-beers/). *WIRED*. Retrieved 13 March 2018.
146. [↑](./Vehicular_automation#cite_ref-146) ["Colorado officer recounts how Otto's autonomous beer delivery became a reality"](http://www.fleetowner.com/autonomous-vehicles/colorado-officer-recounts-how-ottos-autonomous-beer-delivery-became-reality). *Fleet Owner*. 9 March 2018. Retrieved 13 March 2018.
147. [↑](./Vehicular_automation#cite_ref-147) Dillet, Romain. ["Uber acquires Otto to lead Uber's self-driving car effort"](https://techcrunch.com/2016/08/18/uber-acquires-otto-to-lead-ubers-self-driving-car-effort-report-says/). *TechCrunch*. Retrieved 13 March 2018.
148. [↑](./Vehicular_automation#cite_ref-148) McFarland, Matt (26 March 2018). ["First self-drive train launched on mainline track"](https://www.telegraph.co.uk/news/2018/03/26/first-self-drive-train-launched-mainline-track/). *Telegraph*.
149. [↑](./Vehicular_automation#cite_ref-149) Kolodny, Lora (6 February 2018). ["A self-driving truck just drove from Los Angeles to Jacksonville"](https://www.cnbc.com/2018/02/06/embark-trucks-self-driving-truck-drives-los-angeles-to-jacksonville.html). *CNBC*. Retrieved 13 March 2018.
150. [↑](./Vehicular_automation#cite_ref-150) ["A Self-Driving Truck Might Deliver Your Next Refrigerator"](https://www.wired.com/story/embark-self-driving-truck-deliveries/). *WIRED*. Retrieved 13 March 2018.
151. [↑](./Vehicular_automation#cite_ref-151) ["Exclusive: Tesla developing self-driving tech for semi-truck, wants to test in Nevada"](https://www.reuters.com/article/us-tesla-truck-autonomous/exclusive-tesla-developing-self-driving-tech-for-semi-truck-wants-to-test-in-nevada-idUSKBN1AP2GD). *Reuters*. 10 August 2017. Retrieved 8 September 2017.
152. [↑](./Vehicular_automation#cite_ref-152) ["Silicon Valley's Levandowski returns with self-driving truck start-up"](https://www.ft.com/content/9ea9c332-02de-11e9-99df-6183d3002ee1). *Financial Times*. 18 December 2018. [Archived](https://ghostarchive.org/archive/20221211221257/https://www.ft.com/content/9ea9c332-02de-11e9-99df-6183d3002ee1) from the original on 11 December 2022. Retrieved 10 May 2019.
153. [1](./Vehicular_automation#cite_ref-:12_153-0) [2](./Vehicular_automation#cite_ref-:12_153-1) Eric Adams (6 January 2017), ["Honda's self-balancing motorcycle is perfect for noobs"](https://www.wired.com/2017/01/hondas-self-balancing-motorcycle-perfect-noobs/), *Wired*
154. [↑](./Vehicular_automation#cite_ref-154) [*Self-balancing Yamaha motorcycle comes on command*](https://www.iol.co.za/motoring/bikes/self-balancing-yamaha-motorcycle-comes-on-command-12697833), Agence France-Presse, 12 January 2018 – via IOL
155. [↑](./Vehicular_automation#cite_ref-155) Bob Sorokanich (11 September 2018), ["Robots replace humans the one place we least expected: motorcycles"](https://www.roadandtrack.com/new-cars/car-technology/a23083999/bmw-motorrad-self-driving-motorcycle/), *Road and Track*
156. [1](./Vehicular_automation#cite_ref-jalopnik.com_156-0) [2](./Vehicular_automation#cite_ref-jalopnik.com_156-1) ["Harley-Davidson Wants To Make Self-Balancing Motorcycles By Putting A Gyroscope In Your Top Case"](https://jalopnik.com/harley-davidson-wants-to-make-self-balancing-motorcycle-1843958686). *Jalopnik*. 9 June 2020. Retrieved 4 August 2020.
157. [↑](./Vehicular_automation#cite_ref-157) Sorokanich, Bob (11 September 2018). ["Robots Replace Humans the One Place We Least Expected: Motorcycles"](https://www.roadandtrack.com/new-cars/car-technology/a23083999/bmw-motorrad-self-driving-motorcycle/). *Road & Track*. Retrieved 4 August 2020.
158. [↑](./Vehicular_automation#cite_ref-158) ["Self-balancing Yamaha motorcycle comes on command"](https://www.iol.co.za/motoring/bikes/self-balancing-yamaha-motorcycle-comes-on-command-12697833). *www.iol.co.za*. Retrieved 4 August 2020.
159. [↑](./Vehicular_automation#cite_ref-DIAMOND_Online_159-0) 枝久保達也 (25 January 2021). ["世界初の完全自動無人運転、「ポートライナー」が40年前に開業した理由"](https://diamond.jp/articles/-/260574). *diamond.jp* (in Japanese). Diamond. Retrieved 23 January 2022.
160. [↑](./Vehicular_automation#cite_ref-160) Topham, Gwyn (26 March 2018). ["First self-driving train launches on London Thameslink route"](https://www.theguardian.com/business/2018/mar/26/first-self-driving-train-london-thameslink-rail). *The Guardian*.
161. [↑](./Vehicular_automation#cite_ref-161) ["Germany launches world's first autonomous tram in Potsdam"](https://www.theguardian.com/world/2018/sep/23/potsdam-inside-the-worlds-first-autonomous-tram). *[TheGuardian.com](./TheGuardian.com)*. 23 September 2018.
162. [1](./Vehicular_automation#cite_ref-:13_162-0) [2](./Vehicular_automation#cite_ref-:13_162-1) Lee, Jason (23 December 2019). ["3 Companies Looking to Dominate Drone Delivery"](https://www.fool.com/investing/2019/12/23/3-companies-looking-to-dominate-drone-delivery.aspx). *The Motley Fool*. Retrieved 4 August 2020.
163. [↑](./Vehicular_automation#cite_ref-163) ["Toyota Tsusho Launches Drone Delivery of Medical and Pharmaceutical Supplies Business in Nagasaki Prefecture's Goto Islands – Network Powered by Zipline"](https://www.toyota-tsusho.com/english/press/detail/220421_005028.html). *Toyota Tsusho*. Retrieved 21 May 2022.
164. [↑](./Vehicular_automation#cite_ref-164) ["International Commercial Drone Regulation and Drone Delivery Services"](https://www.rand.org/content/dam/rand/pubs/research_reports/RR1700/RR1718z3/RAND_RR1718z3.pdf) (PDF). *RAND*.
165. [↑](./Vehicular_automation#cite_ref-165) ["Bill S. 1405"](https://www.commerce.senate.gov/public/_cache/files/0be741be-c332-47a5-ab62-3edb4f966d22/1D2EF027AE2DDF838BA2C11FF06F00CF.highlights---faa.pdf) (PDF).
166. [↑](./Vehicular_automation#cite_ref-166) ["Home | Boston Dynamics"](https://www.bostondynamics.com/). *www.bostondynamics.com*. Retrieved 4 August 2020.
167. [1](./Vehicular_automation#cite_ref-gov.uk_167-0) [2](./Vehicular_automation#cite_ref-gov.uk_167-1) ["Rules on safe use of automated vehicles on GB roads"](https://www.gov.uk/government/consultations/safe-use-rules-for-automated-vehicles-av/rules-on-safe-use-of-automated-vehicles-on-gb-roads). *GOV.UK*.
168. [1](./Vehicular_automation#cite_ref-:0_168-0) [2](./Vehicular_automation#cite_ref-:0_168-1) Liljamo, Timo; Liimatainen, Heikki; Pöllänen, Markus (November 2018). "Attitudes and concerns on automated vehicles". *Transportation Research Part F: Traffic Psychology and Behaviour*. **59**: 24–44. [Bibcode](./Bibcode_(identifier)):[2018TRPF...59...24L](https://ui.adsabs.harvard.edu/abs/2018TRPF...59...24L). [doi](./Doi_(identifier)):[10.1016/j.trf.2018.08.010](https://doi.org/10.1016%2Fj.trf.2018.08.010). [S2CID](./S2CID_(identifier)) [150232489](https://api.semanticscholar.org/CorpusID:150232489).
169. [1](./Vehicular_automation#cite_ref-:1_169-0) [2](./Vehicular_automation#cite_ref-:1_169-1) ["Despite Autonomous Vehicle Intrigue, Americans Still Crave Control Behind The Wheel, According To New Kelley Blue Book Study"](https://www.prnewswire.com/news-releases/despite-autonomous-vehicle-intrigue-americans-still-crave-control-behind-the-wheel-according-to-new-kelley-blue-book-study-300335413.html) (Press release). Kelley Blue Book. 28 September 2016. [ProQuest](./ProQuest) [1825236192](https://www.proquest.com/docview/1825236192).
170. [1](./Vehicular_automation#cite_ref-:2_170-0) [2](./Vehicular_automation#cite_ref-:2_170-1) [3](./Vehicular_automation#cite_ref-:2_170-2) [4](./Vehicular_automation#cite_ref-:2_170-3) ["Users' Understanding of Automated Vehicles and Perception to Improve Traffic Safety –Results from a National Survey"](https://aaafoundation.org/users-understanding-of-automated-vehicles-and-perception-to-improve-traffic-safety-results-from-a-national-survey/). *AAA Foundation*. 17 December 2019. Retrieved 4 August 2020.
171. [↑](./Vehicular_automation#cite_ref-171) Wang, Song; Li, Zhixia (28 March 2019). ["Exploring the mechanism of crashes with automated vehicles using statistical modeling approaches"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6438496). *PLOS ONE*. **14** (3) e0214550. [Bibcode](./Bibcode_(identifier)):[2019PLoSO..1414550W](https://ui.adsabs.harvard.edu/abs/2019PLoSO..1414550W). [doi](./Doi_(identifier)):[10.1371/journal.pone.0214550](https://doi.org/10.1371%2Fjournal.pone.0214550). [PMC](./PMC_(identifier)) [6438496](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6438496). [PMID](./PMID_(identifier)) [30921396](https://pubmed.ncbi.nlm.nih.gov/30921396).
172. [1](./Vehicular_automation#cite_ref-:3_172-0) [2](./Vehicular_automation#cite_ref-:3_172-1) Ainsalu, Jaagup; Arffman, Ville; Bellone, Mauro; Ellner, Maximilian; Haapamäki, Taina; Haavisto, Noora; Josefson, Ebba; Ismailogullari, Azat; Lee, Bob; Madland, Olav; Madžulis, Raitis; Müür, Jaanus; Mäkinen, Sami; Nousiainen, Ville; Pilli-Sihvola, Eetu; Rutanen, Eetu; Sahala, Sami; Schønfeldt, Boris; Smolnicki, Piotr Marek; Soe, Ralf-Martin; Sääski, Juha; Szymańska, Magdalena; Vaskinn, Ingar; Åman, Milla (2018). ["State of the Art of Automated Buses"](https://doi.org/10.3390%2Fsu10093118). *Sustainability*. **10** (9): 3118. [Bibcode](./Bibcode_(identifier)):[2018Sust...10.3118A](https://ui.adsabs.harvard.edu/abs/2018Sust...10.3118A). [doi](./Doi_(identifier)):[10.3390/su10093118](https://doi.org/10.3390%2Fsu10093118).
173. [↑](./Vehicular_automation#cite_ref-173) ["Collision Between Vehicle Controlled by Developmental Automated Driving System and Pedestrian"](https://www.ntsb.gov/investigations/Pages/HWY18MH010.aspx). *[National Transportation Safety Board](./National_Transportation_Safety_Board)*. 28 March 2018. Retrieved 19 February 2023.
174. [1](./Vehicular_automation#cite_ref-:4_174-0) [2](./Vehicular_automation#cite_ref-:4_174-1) [3](./Vehicular_automation#cite_ref-:4_174-2) Dogan, E; Chatila, R (2016). ["Ethics in the design of automated vehicles: the AVEthics project"](http://ceur-ws.org/Vol-1668/paper2.pdf) (PDF). *CEUR Workshop Proceedings*.
175. [1](./Vehicular_automation#cite_ref-:5_175-0) [2](./Vehicular_automation#cite_ref-:5_175-1) [3](./Vehicular_automation#cite_ref-:5_175-2) "How Should Autonomous Vehicles Make Moral Decisions? Machine Ethics, Artificial Driving Intelligence, and Crash Algorithms". *Contemporary Readings in Law and Social Justice*. **11**: 9. 2019. [doi](./Doi_(identifier)):[10.22381/CRLSJ11120191](https://doi.org/10.22381%2FCRLSJ11120191) (inactive 1 July 2025). [S2CID](./S2CID_(identifier)) [213759514](https://api.semanticscholar.org/CorpusID:213759514). [ProQuest](./ProQuest) [2269349615](https://www.proquest.com/docview/2269349615).`{{cite journal}}`:  CS1 maint: DOI inactive as of July 2025 ([link](./Category:CS1_maint:_DOI_inactive_as_of_July_2025))
176. [1](./Vehicular_automation#cite_ref-:6_176-0) [2](./Vehicular_automation#cite_ref-:6_176-1) "The Safety and Reliability of Networked Autonomous Vehicles: Ethical Dilemmas, Liability Litigation Concerns, and Regulatory Issues". *Contemporary Readings in Law and Social Justice*. **11** (2): 9. 2019. [doi](./Doi_(identifier)):[10.22381/CRLSJ11220191](https://doi.org/10.22381%2FCRLSJ11220191). [ProQuest](./ProQuest) [2322893910](https://www.proquest.com/docview/2322893910).
177. [↑](./Vehicular_automation#cite_ref-177) Umbrello, Steven; Yampolskiy, Roman V. (15 May 2021). "Designing AI for Explainability and Verifiability: A Value Sensitive Design Approach to Avoid Artificial Stupidity in Autonomous Vehicles". *International Journal of Social Robotics*. **14** (2): 313–322. [doi](./Doi_(identifier)):[10.1007/s12369-021-00790-w](https://doi.org/10.1007%2Fs12369-021-00790-w). [hdl](./Hdl_(identifier)):[2318/1788856](https://hdl.handle.net/2318%2F1788856). [ISSN](./ISSN_(identifier)) [1875-4805](https://search.worldcat.org/issn/1875-4805). [S2CID](./S2CID_(identifier)) [236584241](https://api.semanticscholar.org/CorpusID:236584241).

 

## Works cited

 
- ["Uber Self-Driving Cars Hit The Streets Of Pittsburgh"](https://www.cbsnews.com/pittsburgh/news/uber-driverless-cars-hit-the-streets-of-pittsburgh/). *www.cbsnews.com*. 14 September 2016. Retrieved 5 May 2023.
- Badue, Claudine; Guidolini, Rânik; Carneiro, Raphael Vivacqua; Azevedo, Pedro; Cardoso, Vinicius B.; Forechi, Avelino; Jesus, Luan; Berriel, Rodrigo; Paixão, Thiago M.; Mutz, Filipe; de Paula Veronese, Lucas; Oliveira-Santos, Thiago; De Souza, Alberto F. (1 March 2021). "Self-driving cars: A survey". *Expert Systems with Applications*. **165** 113816. [Elsevier](./Elsevier). [arXiv](./ArXiv_(identifier)):[1901.04407](https://arxiv.org/abs/1901.04407). [doi](./Doi_(identifier)):[10.1016/j.eswa.2020.113816](https://doi.org/10.1016%2Fj.eswa.2020.113816).
- Azam, Shoaib; Munir, Farzeen; Sheri, Ahmad Muqeem; Kim, Joonmo; Jeon, Moongu (22 October 2020). ["System, Design and Experimental Validation of Autonomous Vehicle in an Unconstrained Environment"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7660187). *[Sensors](./Sensors_(journal))*. **20** (21): 5999. [Bibcode](./Bibcode_(identifier)):[2020Senso..20.5999A](https://ui.adsabs.harvard.edu/abs/2020Senso..20.5999A). [doi](./Doi_(identifier)):[10.3390/s20215999](https://doi.org/10.3390%2Fs20215999). [PMC](./PMC_(identifier)) [7660187](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7660187). [PMID](./PMID_(identifier)) [33105897](https://pubmed.ncbi.nlm.nih.gov/33105897).
- Serban, Alex; Poll, Erik; Visser, Joost (2020). ["A Standard Driven Software Architecture for Fully Autonomous Vehicles"](https://doi.org/10.2991%2Fjase.d.200212.001). *Journal of Automotive Software Engineering*. **1** (1). [Atlantis Press](./Atlantis_Press): 20. [doi](./Doi_(identifier)):[10.2991/jase.d.200212.001](https://doi.org/10.2991%2Fjase.d.200212.001).

 

## External links

 
- [European Commission Intelligent Car website](http://ec.europa.eu/information_society/activities/intelligentcar/index_en.htm)
- [U.S. Department of Transportation – Intelligent Transportation Systems Joint Program Office website](https://web.archive.org/web/20141129013957/http://www.its.dot.gov/automated_vehicle/index.htm)
- Sheth, Aadit (3 January 2024). ["Indian AI And Robotics Startup Claims Level 5 Autonomy"](https://www.neatprompts.com/p/indian-ai-and-robotics-startup-claims-level-5-autonomy). *Prompt Engineering Daily*. Retrieved 27 January 2024.