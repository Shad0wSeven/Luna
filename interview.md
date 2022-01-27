# what Charles has said 

1 laser shooting 

- 10km low power laser
- atmospheric scattering
- vibrations - transmitter
- high wind
- Raspberry pi gpio speed - maybe use if they ask?
- 3D Printing -> more precision, long time, smaller nozzle
- adjustment in the lens mounts? (easy)

## atmospheric scattering

not really a problem, 90% of light makes it from the top of the atmosphere to the bottom, which is much more air volume, even accounting for density differences, according to papers, and accounting for ground level Raleigh scattering, its like something like 90-95% transmission at 20km.

### atmospheric refraction

not really an issue, as this mostly happens at really really long distances and different density, air pockets shouldn't significantly change this.

## issues with dust and whatnot

dust will inevitably be an issue, but to be honest, in the worst areas, in places like Africa where this is targeted at, there's maximum around 20 days of rain, and having 20 days of downtime (which is highly unlikely as rain would only be on the devices for very little time) 365 days of downtime is a lot worse. 

rainfall average is something like 250 hours, so that's around 250 hours of downtime across rainy days in total.

dust storms and fog are less of an issue, as these are obv very rare

fog is onyl an issue near coastal areas, and these tend to be more prosperous and close to civilization anyways. anywhere with fog above 20 days of the year (and keep in mind this is just a couple of horus in the morning) is going to be very close to the coast. dust storms are also quite rare

even deployment in somewhere like a tropical rainforest, only around 1500 hours of the 8500 hours in a year would be lost, significant sure, but for the raniest place in the earth yeah.

dust areosols shoulndt block the entire beam anyways

and the 3x

### cleaning and rearming

honestly i'm more scared of dust and water piling up and covering equipment 

water can be mitigated with a hydrophobic coating, but the real issue is dust

### aiming issues

a laser beam becoming misaligned due to wind is not really a huge issue, a sturdy metal pole and a laser attached to a metal frame in production should be more than enough to sustain winds in excess of 40-50 mph, and these types of storms are so rare, mostly tornadoes or hurricanes, both of which are not going to affect areas where this tech would be installed. 

I mean with global warming that might change in a couple of decades but yeah hopefully we can turn it around before then.



# laser setup

---

## divergence and beam size

- basically, collimated to around 1 mm, then expanded to 37.5 mm, ![msedge_zdjoD36XcW](C:\Users\Ayush Nayak\Documents\ShareX\Screenshots\2022-01\msedge_zdjoD36XcW.png)

  ![image-20220126182530877](C:\Users\Ayush Nayak\AppData\Roaming\Typora\typora-user-images\image-20220126182530877.png)

also bring up nasa spacecraft transmission

## beam expander

talk about focal lengths

gallilean

![image-20220126183217389](C:\Users\Ayush Nayak\AppData\Roaming\Typora\typora-user-images\image-20220126183217389.png)

500nm and 6nm

41.6x expansion **SEMI ERROR** (say took 10% error in measurements to be reasonable)

**MAJOR HOLE**: 6 nm measured beam, collimated to 1 mm... actual expansion around 0.112

the beam expansion should be around 1 mm, maximum 50mm outside of final expander although should be lower



### lenses

for Galilean plano convex second lens biconcave first one for transmitting data

collimation initial beam smaller, easier to spread out later on, made for focusing beam right after the initial laser head, due to these diodes being really "crude" if you will

## laser switching

diode lasers can be switched extremally fast by switching injection current, ns time.

84 mhz

### laser modulator

talk about fiber optics

renesas square wave ISL78365ARZ-T7A, but modulation obviously only u to about 15-20 mbps from arduino due, 

due digital pins

raspberry pi for reaching that 200mbps

arduinos simpler to work with so wanted to test with that

## phototransistor switching

Osram SFH3410, switches very fast up to around **70 mhz, so around 20 mbps**

hitting 200 is possible with amplificaiton and hardware meant by introducing renesas module

phototransistor more power output doesnt need to be amplified less noise

[Thorlabs - FDS100-P10 Si Photodiode, 10 ns Rise Time, 350 - 1100 nm, 3.6 mm x 3.6 mm Active Area, 10 Pack](https://www.thorlabs.com/thorproduct.cfm?partnumber=FDS100-P10)

throw out you can just grab a photodiode harder to interface, like 10ns rise time good for like 100mbps

in a gridlike array to grab light across the spectrum



astronomical filter 488 nm to filter light into just a narrow band

# mounting

---

mounting itself is on a slab, it must be around 70cm, which is decently long, planning on testing it indoors and in large open areas with a plank of plywood, and 3d printed enclosures to keep the lenses safe. for a production model, it's definitely going to need some metal.



3d printed rings

alumnium extrusion

60cm, intermediary ring in the middle

## laser aiming

### telescope

mount telescope to bottom of device thinking about aiming 



recieving end



### lora

lora is useful for communicating whether on or off. between the radios, also when things get misaligned, or just general diagnostics information

its good for around 20km and even more, its just extremally slow, 

## solar power stuff

solar panel attached, 25w, laser should take max around 1w and the Arduino around 0.27W, overkill because useful for quickly charging batteries to maximum when needed, also for supporting more hardware

### servos

so obviously think itself is more about what I think i can build, and I wanted to mostly focus on getting the core of the project, the laser data transmission working, but also really build in 0 bottlenecks, so everything can easily scale to even better

so for aiming, of course i would have two people, with radios working to aim while testing the device. but i also built in LoRa, and added that to power 

# other stuff

---

how will think help you

- obviously the mentorship

what have you done

what do you need from us

- mentorship money

what are your qualifications to manufacture

- CubeSat
- telescope rebuilding optics (ik its mirrors not really reflectors)

challenges might face

- fog
- re-aiming

challenges faced

doesn't work what's plan b, look for alternatives

waht people might u do

