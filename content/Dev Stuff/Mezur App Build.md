---
draft: false
tags:
  - dev
  - seam-app
  - wip
---
Kat, upon seeing the workflow: 
>Yoooo that looks awesome. The workflow sounds exactly like what I was hoping for!

## Information Architecture

### Model Profiles
- Can create, read, update, delete
- Names of people being measured
- Lists known measurements
- Keeps track of, but does not list unknown measurements (unless toggled)

### Garments
- Can create, read, update, delete
- Garments store a list of measurements needed
- Garments can be shared among Model Profiles
- Garments will flag if unknown measurements are needed (in order to successfully make the garment)
- Garments can have their list of needed measurements updated

### Measurements
| Area                             | Measurement Description                                 |
| -------------------------------- | ------------------------------------------------------- |
| **Neck**                         | Around the base of the neck.                            |
| **Shoulder Width**               | Across the back, shoulder tip to tip.                   |
| **Bust/Chest**                   | Fullest part of the bust/chest, around the back.        |
| **High Bust**                    | Just above the bust, under the arms.                    |
| **Underbust**                    | Around the ribcage, just under the bust.                |
| **Waist**                        | Natural waistline, typically the narrowest part.        |
| **High Waist**                   | Just above the natural waist.                           |
| **Hip (Full/Low)**               | Fullest part of the hips and buttocks.                  |
| **High Hip**                     | Around 3–4" below the waist.                            |
| **Thigh**                        | Fullest part of one thigh.                              |
| **Knee**                         | Around the knee cap.                                    |
| **Calf**                         | Fullest part of the calf.                               |
| **Ankle**                        | Around the ankle.                                       |
| **Inseam**                       | From crotch to ankle along the inside leg.              |
| **Outseam**                      | From waist to ankle along the outside leg.              |
| **Torso Length**                 | From high shoulder point to waist.                      |
| **Back Waist Length**            | From nape to waist along the spine.                     |
| **Front Waist Length**           | From shoulder (near neck) to waist over the bust.       |
| **Arm Length**                   | From shoulder to wrist with bent elbow.                 |
| **Upper Arm (Bicep)**            | Fullest part of the upper arm.                          |
| **Wrist**                        | Around the wrist bone.                                  |
| **Shoulder to Bust**             | From shoulder to bust point.                            |
| **Bust Point to Bust Point**     | Distance between apexes of the bust.                    |
| **Shoulder to Shoulder (Front)** | Across the front from shoulder joint to shoulder joint. |
## Functions

### Login
- Secure authentication (through Google, Facebook, or email address)
- Cloud access/storage
- Can logout or delete account

### Models
- Can be created, read, updated, or deleted
- Data includes
	- Name
	- Measurements
- Measurements can be created, read, updated, or deleted
- When a GARMENT is being made for a MODEL, the model's MEASUREMENTS are called for the GARMENT

### Garments
- Can be created, read, updated, or deleted
- Include a list of MEASUREMENTS needed
- Alerts user if MEASUREMENTS are missing
- Some MEASUREMENTS may be OPTIONAL
- Garments can be copied/used as a template
- The two started templates are SHIRT and PANTS

| Measurement                      | Shirt ✅  | Pants ✅  | Notes                              |
| -------------------------------- | -------- | -------- | ---------------------------------- |
| **Neck**                         | ✅        |          | For collars.                       |
| **Shoulder Width**               | ✅        |          | Defines sleeve/shoulder fit.       |
| **Bust/Chest**                   | ✅        |          | Critical for shirt body.           |
| **High Bust**                    | Optional |          | Useful for fitted tops.            |
| **Underbust**                    | Optional |          | Needed for very fitted shirts.     |
| **Waist (Natural)**              | ✅        | ✅        | Key for shirt length & pants rise. |
| **High Waist**                   | Optional | ✅        | Helps with high-rise pants.        |
| **Hip (Full)**                   | ✅        | ✅        | Shirt hem fit & pants seat.        |
| **High Hip**                     |          | Optional | Helpful for curved waistbands.     |
| **Thigh**                        |          | ✅        | For pants fit.                     |
| **Knee**                         |          | ✅        | Shaping below thigh.               |
| **Calf**                         |          | Optional | Important for slim/skinny styles.  |
| **Ankle**                        |          | ✅        | For hem width.                     |
| **Inseam**                       |          | ✅        | Inner leg length.                  |
| **Outseam**                      |          | ✅        | Total pant length.                 |
| **Torso Length**                 | ✅        |          | For shirt fit & tuck length.       |
| **Back Waist Length**            | ✅        |          | Ensures proper shirt drape.        |
| **Front Waist Length**           | ✅        |          | Important for bust shaping.        |
| **Arm Length**                   | ✅        |          | For long sleeves.                  |
| **Upper Arm (Bicep)**            | ✅        |          | Sleeve comfort.                    |
| **Wrist**                        | ✅        |          | For cuff fitting.                  |
| **Shoulder to Bust**             | ✅        |          | Helps shape fitted bodices.        |
| **Bust Point to Point**          | ✅        |          | Needed for dart placement.         |
| **Shoulder to Shoulder (Front)** | ✅        |          | Affects front shirt fit.           |
- **Shirt Essentials**: Neck, Shoulder Width, Chest, Waist, Hip, Arm Length, Upper Arm, Wrist, Torso Length, Back/Front Waist Length.
- **Pants Essentials**: Waist, Hip, Thigh, Knee, Ankle, Inseam, Outseam.


## Case Study

### User Persona - Kat Fiero

#### About
**Age**: Mid-thirties
**Education**: GED
**Status**: Married
**Occupation**: Seamstress
**Location**: Las Vegas
**Tech Literacy**: High

#### Bio
Kat is a skilled seamstress and maker based in Las Vegas, specializing in custom clothing and cosplay commissions for both friends and clients. Highly creative and detail-oriented, she juggles multiple artistic hobbies that demand strong organizational systems to manage her time, materials, and project workflows effectively.

#### Core Needs
- Store and manage individual client measurements for future use
- Create reusable measurement templates tailored to specific garment types
- Quickly identify which measurements are missing for any given project

#### Frustrations
- Forgets which measurements she’s already taken for returning clients
- Worries about seeming disorganized or unprofessional    
- Lacks an easy way to determine which measurements are needed for different garment types


### Empathy Map

#### User Does
- Writes measurements on paper scraps or notes app

#### User Thinks
- What measurements did I already take?
- What measurements am I missing?
- Where did I save the measurements I have?
- What measurements are needed for specific clothing?

#### User Feels
- Unconfident
- Confused

#### User Says
- "I keep losing track of what measurements I have"
- "I don't want to bother my clients"
- "I know I had their measurements somewhere, I just don't know where I put it"

### User Journey Map

**User:** Kat Fiero
**Scenario**: Kat wants to take down measurements to make a shirt for a new client
**Expectations**: This app will allow Kat to quickly take all necessary measurements to make her client a shirt, and will save that client's measurements for any future projects


|               | Open App                                                               | Add Client                                    | Select Garment | Record Measurements                                                                                                                                             |
| ------------- | ---------------------------------------------------------------------- | --------------------------------------------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Touchpoints   | Needs to take measurements for a new garment, or updating measurements | When adding new client, previously unmeasured |                | Opened while measuring                                                                                                                                          |
| Actions       | Log in to account                                                      | Add new client. Record Name.                  |                |                                                                                                                                                                 |
| Painpoints    | Any log-in issues                                                      |                                               |                |                                                                                                                                                                 |
| Emotions      | Excitement                                                             |                                               |                |                                                                                                                                                                 |
| Opportunities |                                                                        | Record any notes on clothing/style preference |                | After measurements recorded, notification that "Model needs just # more measurements to make a **NEW GARMENT**" (Encourages more measurements while convenient) |
|               |                                                                        |                                               |                |                                                                                                                                                                 |
## Information Architecture

### Model Profiles
- Can create, read, update, delete
- Names of people being measured
- Lists known measurements
- Keeps track of, but does not list unknown measurements (unless toggled)

### Garments
- Can create, read, update, delete
- Garments store a list of measurements needed
- Garments can be shared among Model Profiles
- Garments will flag if unknown measurements are needed (in order to successfully make the garment)
- Garments can have their list of needed measurements updated

### Measurements
| Area                             | Measurement Description                                 |
| -------------------------------- | ------------------------------------------------------- |
| **Neck**                         | Around the base of the neck.                            |
| **Shoulder Width**               | Across the back, shoulder tip to tip.                   |
| **Bust/Chest**                   | Fullest part of the bust/chest, around the back.        |
| **High Bust**                    | Just above the bust, under the arms.                    |
| **Underbust**                    | Around the ribcage, just under the bust.                |
| **Waist**                        | Natural waistline, typically the narrowest part.        |
| **High Waist**                   | Just above the natural waist.                           |
| **Hip (Full/Low)**               | Fullest part of the hips and buttocks.                  |
| **High Hip**                     | Around 3–4" below the waist.                            |
| **Thigh**                        | Fullest part of one thigh.                              |
| **Knee**                         | Around the knee cap.                                    |
| **Calf**                         | Fullest part of the calf.                               |
| **Ankle**                        | Around the ankle.                                       |
| **Inseam**                       | From crotch to ankle along the inside leg.              |
| **Outseam**                      | From waist to ankle along the outside leg.              |
| **Torso Length**                 | From high shoulder point to waist.                      |
| **Back Waist Length**            | From nape to waist along the spine.                     |
| **Front Waist Length**           | From shoulder (near neck) to waist over the bust.       |
| **Arm Length**                   | From shoulder to wrist with bent elbow.                 |
| **Upper Arm (Bicep)**            | Fullest part of the upper arm.                          |
| **Wrist**                        | Around the wrist bone.                                  |
| **Shoulder to Bust**             | From shoulder to bust point.                            |
| **Bust Point to Bust Point**     | Distance between apexes of the bust.                    |
| **Shoulder to Shoulder (Front)** | Across the front from shoulder joint to shoulder joint. |
## Functions

### Login
- Secure authentication (through Google, Facebook, or email address)
- Cloud access/storage
- Can logout or delete account

### Models
- Can be created, read, updated, or deleted
- Data includes
	- Name
	- Measurements
- Measurements can be created, read, updated, or deleted
- When a GARMENT is being made for a MODEL, the model's MEASUREMENTS are called for the GARMENT

### Garments
- Can be created, read, updated, or deleted
- Include a list of MEASUREMENTS needed
- Alerts user if MEASUREMENTS are missing
- Some MEASUREMENTS may be OPTIONAL
- Garments can be copied/used as a template
- The two started templates are SHIRT and PANTS

| Measurement                      | Shirt ✅  | Pants ✅  | Notes                              |
| -------------------------------- | -------- | -------- | ---------------------------------- |
| **Neck**                         | ✅        |          | For collars.                       |
| **Shoulder Width**               | ✅        |          | Defines sleeve/shoulder fit.       |
| **Bust/Chest**                   | ✅        |          | Critical for shirt body.           |
| **High Bust**                    | Optional |          | Useful for fitted tops.            |
| **Underbust**                    | Optional |          | Needed for very fitted shirts.     |
| **Waist (Natural)**              | ✅        | ✅        | Key for shirt length & pants rise. |
| **High Waist**                   | Optional | ✅        | Helps with high-rise pants.        |
| **Hip (Full)**                   | ✅        | ✅        | Shirt hem fit & pants seat.        |
| **High Hip**                     |          | Optional | Helpful for curved waistbands.     |
| **Thigh**                        |          | ✅        | For pants fit.                     |
| **Knee**                         |          | ✅        | Shaping below thigh.               |
| **Calf**                         |          | Optional | Important for slim/skinny styles.  |
| **Ankle**                        |          | ✅        | For hem width.                     |
| **Inseam**                       |          | ✅        | Inner leg length.                  |
| **Outseam**                      |          | ✅        | Total pant length.                 |
| **Torso Length**                 | ✅        |          | For shirt fit & tuck length.       |
| **Back Waist Length**            | ✅        |          | Ensures proper shirt drape.        |
| **Front Waist Length**           | ✅        |          | Important for bust shaping.        |
| **Arm Length**                   | ✅        |          | For long sleeves.                  |
| **Upper Arm (Bicep)**            | ✅        |          | Sleeve comfort.                    |
| **Wrist**                        | ✅        |          | For cuff fitting.                  |
| **Shoulder to Bust**             | ✅        |          | Helps shape fitted bodices.        |
| **Bust Point to Point**          | ✅        |          | Needed for dart placement.         |
| **Shoulder to Shoulder (Front)** | ✅        |          | Affects front shirt fit.           |
- **Shirt Essentials**: Neck, Shoulder Width, Chest, Waist, Hip, Arm Length, Upper Arm, Wrist, Torso Length, Back/Front Waist Length.
- **Pants Essentials**: Waist, Hip, Thigh, Knee, Ankle, Inseam, Outseam.


## Case Study

### User Persona - Kat Fiero

#### About
**Age**: Mid-thirties
**Education**: GED
**Status**: Married
**Occupation**: Seamstress
**Location**: Las Vegas
**Tech Literacy**: High

#### Bio
Kat is a skilled seamstress and maker based in the southwest, specializing in custom clothing and cosplay commissions for both friends and clients. Highly creative and detail-oriented, she juggles multiple artistic hobbies that demand strong organizational systems to manage her time, materials, and project workflows effectively.

#### Core Needs
- Store and manage individual client measurements for future use
- Create reusable measurement templates tailored to specific garment types
- Quickly identify which measurements are missing for any given project

#### Frustrations
- Forgets which measurements she’s already taken for returning clients
- Worries about seeming disorganized or unprofessional    
- Lacks an easy way to determine which measurements are needed for different garment types


### Empathy Map

#### User Does
- Writes measurements on paper scraps or notes app

#### User Thinks
- What measurements did I already take?
- What measurements am I missing?
- Where did I save the measurements I have?
- What measurements are needed for specific clothing?

#### User Feels
- Unconfident
- Confused
- Curious
- Excited 

#### User Says
- "I keep losing track of what measurements I have"
- "I don't want to bother my clients"
- "I know I had their measurements somewhere, I just don't know where I put it"

### User Journey Map

**User:** Kat Fiero
**Scenario**: Kat wants to take down measurements to make a shirt for a new client
**Expectations**: This app will allow Kat to quickly take all necessary measurements to make her client a shirt, and will save that client's measurements for any future projects


|               | Open App                                                               | Add Client                                    | Select Garment                                                                    | Record / View Measurements                                                                                                                                      |
| ------------- | ---------------------------------------------------------------------- | --------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Touchpoints   | Needs to take measurements for a new garment, or updating measurements | When adding new client, previously unmeasured | When creating specific clothing item                                              | Opened while measuring                                                                                                                                          |
| Actions       | Log in to account                                                      | Add new client. Record Name.                  | Determine item to make                                                            | See what measurements are needed.                                                                                                                               |
| Painpoints    | Any log-in issues                                                      | How easy is it to find an existing model?     | How challenging is it to determine what measurements are needed for what garment? |                                                                                                                                                                 |
| Emotions      | Excitement                                                             | Hope                                          | Confusion                                                                         | Satisfaction                                                                                                                                                    |
| Opportunities |                                                                        | Record any notes on clothing/style preference |                                                                                   | After measurements recorded, notification that "Model needs just # more measurements to make a **NEW GARMENT**" (Encourages more measurements while convenient) |
|               |                                                                        |                                               |                                                                                   |                                                                                                                                                                 |
## Information Architecture

### Model Profiles
- Can create, read, update, delete
- Names of people being measured
- Lists known measurements
- Keeps track of, but does not list unknown measurements (unless toggled)

### Garments
- Can create, read, update, delete
- Garments store a list of measurements needed
- Garments can be shared among Model Profiles
- Garments will flag if unknown measurements are needed (in order to successfully make the garment)
- Garments can have their list of needed measurements updated

### Measurements
| Area                             | Measurement Description                                 |
| -------------------------------- | ------------------------------------------------------- |
| **Neck**                         | Around the base of the neck.                            |
| **Shoulder Width**               | Across the back, shoulder tip to tip.                   |
| **Bust/Chest**                   | Fullest part of the bust/chest, around the back.        |
| **High Bust**                    | Just above the bust, under the arms.                    |
| **Underbust**                    | Around the ribcage, just under the bust.                |
| **Waist**                        | Natural waistline, typically the narrowest part.        |
| **High Waist**                   | Just above the natural waist.                           |
| **Hip (Full/Low)**               | Fullest part of the hips and buttocks.                  |
| **High Hip**                     | Around 3–4" below the waist.                            |
| **Thigh**                        | Fullest part of one thigh.                              |
| **Knee**                         | Around the knee cap.                                    |
| **Calf**                         | Fullest part of the calf.                               |
| **Ankle**                        | Around the ankle.                                       |
| **Inseam**                       | From crotch to ankle along the inside leg.              |
| **Outseam**                      | From waist to ankle along the outside leg.              |
| **Torso Length**                 | From high shoulder point to waist.                      |
| **Back Waist Length**            | From nape to waist along the spine.                     |
| **Front Waist Length**           | From shoulder (near neck) to waist over the bust.       |
| **Arm Length**                   | From shoulder to wrist with bent elbow.                 |
| **Upper Arm (Bicep)**            | Fullest part of the upper arm.                          |
| **Wrist**                        | Around the wrist bone.                                  |
| **Shoulder to Bust**             | From shoulder to bust point.                            |
| **Bust Point to Bust Point**     | Distance between apexes of the bust.                    |
| **Shoulder to Shoulder (Front)** | Across the front from shoulder joint to shoulder joint. |
## Functions

### Login
- Secure authentication (through Google, Facebook, or email address)
- Cloud access/storage
- Can logout or delete account

### Models
- Can be created, read, updated, or deleted
- Data includes
	- Name
	- Measurements
- Measurements can be created, read, updated, or deleted
- When a GARMENT is being made for a MODEL, the model's MEASUREMENTS are called for the GARMENT

### Garments
- Can be created, read, updated, or deleted
- Include a list of MEASUREMENTS needed
- Alerts user if MEASUREMENTS are missing
- Some MEASUREMENTS may be OPTIONAL
- Garments can be copied/used as a template
- The two started templates are SHIRT and PANTS

| Measurement                      | Shirt ✅  | Pants ✅  | Notes                              |
| -------------------------------- | -------- | -------- | ---------------------------------- |
| **Neck**                         | ✅        |          | For collars.                       |
| **Shoulder Width**               | ✅        |          | Defines sleeve/shoulder fit.       |
| **Bust/Chest**                   | ✅        |          | Critical for shirt body.           |
| **High Bust**                    | Optional |          | Useful for fitted tops.            |
| **Underbust**                    | Optional |          | Needed for very fitted shirts.     |
| **Waist (Natural)**              | ✅        | ✅        | Key for shirt length & pants rise. |
| **High Waist**                   | Optional | ✅        | Helps with high-rise pants.        |
| **Hip (Full)**                   | ✅        | ✅        | Shirt hem fit & pants seat.        |
| **High Hip**                     |          | Optional | Helpful for curved waistbands.     |
| **Thigh**                        |          | ✅        | For pants fit.                     |
| **Knee**                         |          | ✅        | Shaping below thigh.               |
| **Calf**                         |          | Optional | Important for slim/skinny styles.  |
| **Ankle**                        |          | ✅        | For hem width.                     |
| **Inseam**                       |          | ✅        | Inner leg length.                  |
| **Outseam**                      |          | ✅        | Total pant length.                 |
| **Torso Length**                 | ✅        |          | For shirt fit & tuck length.       |
| **Back Waist Length**            | ✅        |          | Ensures proper shirt drape.        |
| **Front Waist Length**           | ✅        |          | Important for bust shaping.        |
| **Arm Length**                   | ✅        |          | For long sleeves.                  |
| **Upper Arm (Bicep)**            | ✅        |          | Sleeve comfort.                    |
| **Wrist**                        | ✅        |          | For cuff fitting.                  |
| **Shoulder to Bust**             | ✅        |          | Helps shape fitted bodices.        |
| **Bust Point to Point**          | ✅        |          | Needed for dart placement.         |
| **Shoulder to Shoulder (Front)** | ✅        |          | Affects front shirt fit.           |
- **Shirt Essentials**: Neck, Shoulder Width, Chest, Waist, Hip, Arm Length, Upper Arm, Wrist, Torso Length, Back/Front Waist Length.
- **Pants Essentials**: Waist, Hip, Thigh, Knee, Ankle, Inseam, Outseam.


## Case Study

### User Persona - Kat Fiero

#### About
**Age**: Mid-thirties
**Education**: GED
**Status**: Married
**Occupation**: Seamstress
**Location**: Las Vegas
**Tech Literacy**: High

#### Bio
Kat is a skilled seamstress and maker based in Las Vegas, specializing in custom clothing and cosplay commissions for both friends and clients. Highly creative and detail-oriented, she juggles multiple artistic hobbies that demand strong organizational systems to manage her time, materials, and project workflows effectively.

#### Core Needs
- Store and manage individual client measurements for future use
- Create reusable measurement templates tailored to specific garment types
- Quickly identify which measurements are missing for any given project

#### Frustrations
- Forgets which measurements she’s already taken for returning clients
- Worries about seeming disorganized or unprofessional    
- Lacks an easy way to determine which measurements are needed for different garment types


### Empathy Map

#### User Does
- Writes measurements on paper scraps or notes app

#### User Thinks
- What measurements did I already take?
- What measurements am I missing?
- Where did I save the measurements I have?
- What measurements are needed for specific clothing?

#### User Feels
- Unconfident
- Confused

#### User Says
- "I keep losing track of what measurements I have"
- "I don't want to bother my clients"
- "I know I had their measurements somewhere, I just don't know where I put it"

### User Journey Map  
**Scenario:** Kat wants to take down measurements to make a shirt for a new client.

| **Stage**         | **Goal**                                    | **Actions**                                               | **Thinks**                                                    | **Feels**                | **Pain Points**                                                  | **Opportunities**                                                           |
| ----------------- | ------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------- | ------------------------ | ---------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Open App          | Access measurement tool quickly             | Launches the app, logs in or uses quick access            | "Hope this doesn't take long to get into."                    | Neutral / Anticipating   | Log-in friction, slow loading                                    | Persistent login, Face ID, or offline mode                                  |
| Add Client        | Start a new profile for the client          | Taps “Add New Model,” enters client name                  | "Let’s get their profile set up now so I don’t forget later." | Focused                  | May forget to take notes on style preferences                    | Prompt for custom notes (e.g., “style notes,” “client quirks”)              |
| Select Garment    | Identify what measurements are needed       | Chooses “Shirt” template from list                        | "Which measurements are needed for a shirt again?"            | Slightly unsure          | Uncertainty about which measurements are required                | Visual checklist of required/optional fields with progress bar              |
| Take Measurements | Record all needed data                      | Enters measurements one by one, checking off the list     | "Did I already take this one?" or "Am I missing any?"         | In control, but cautious | Risk of skipping or duplicating measurements                     | Smart alerts: “X of 15 completed,” “You’re missing these measurements”      |
| Save & Confirm    | Make sure all info is captured and reusable | Hits “Save,” gets confirmation popup                      | "Okay, done for now. I’ll reuse this profile next time."      | Confident, relieved      | Fear of data loss or forgetting what’s missing                   | Auto-sync with cloud, optional reminder: “Want to set a follow-up fitting?” |
| Reuse Later       | Use saved measurements for future garments  | Opens client profile and selects a different garment type | "Do I need to take more measurements for this?"               | Productive               | Doesn’t know if additional data is needed for different garments | Alert: “You have 3 of 8 needed pants measurements—want to add them now?”    |
|                   |                                             |                                                           |                                                               |                          |                                                                  |                                                                             |

### Flowchart

![[Mezur App Flowchart.png]]

### Low-Fidelity Prototype

![[Low-Fi Prototype.mov]]

### High-Fidelity Prototype

Figma Link goes here

#### Brand Notes
- Animal Crossing mixed with Stardew Valley aesthetic
- Paper, cloth, crafty visuals
- Relaxed, unintrusive environment