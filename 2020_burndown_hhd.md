# HHD Burndown List: Soft Delivery (July 29, 2020)

## Data Explorer (Dashboard)

### Map
  - [ ] Display projects on map
  - [ ] Display instruments on map
 
### Plots
  - [ ] Timeseries Plots
    - [ ] Show rainfall on separate plot window
    - [ ] Show Pool/Tail on plot
  - [ ] Correlation Plots
  - [ ] API: Transform raw measurements into elevation
    What is the common parameter? `elevation-water`
  
### API Endpoint for fetching many timeseries
  
  - [ ] `<POST> /instrumentation/explorer?parameter_id=<uuid>`
  
  Notes: 

  * Client to Send JSON: Instrument IDs `[ <uuid>, <uuid>, ]`
  
  * Server to Send JSON:
  
    ```
    { <instrument_id>: {
        <timeseries_id>: [
          { <time>: <value> },
          { <time>: <value> },
          { <time>: <value> }
        ],
        <timeseries_id>: [
          { <time>: <value> },
          { <time>: <value> },
          { <time>: <value> }
        ],
      },
      <instrument_id>: {...
      }
    }    
    ```

## Data Import/Export

- [ ] Import Instruments

    - [ ] Import validation: Check names to be uploaded via POST
  
    Optional Fields: 
        Allow multiple coordinate systems. Must supply an EPSG Code.
  
- [ ] Import Timeseries Measurements

         Note: Timeseries must exist to upload measurements.
         Will have button to create new timeseries in uploader.
   
- [ ] Export Instruments (csv)
- [ ] Export Timeseries  (csv)

## Timeseries text for plot annotations

- [ ] Instrument Notes
- [ ] Thresholds `{ type: above (below, at), name: "Action Stage"}` or similar? (if we have time)

## Finalize Roles (permissions)
        
- [ ] Project Level Privileges

  * **ProjectAdmin**
  
    Can Manage Instruments, Instrument Groups
    Delete capability
  
  * **ProjectMember**
  
       Can Add Timeseries Data

  * **ApplicationAdmin**
      
    Can modify user roles
    Can create projects

   * **isLoggedIn** : No roles
   * **Anon**       : Not Logged In (general public)
   
## Real Time Data Acquisition

- [ ] Get it running in the cloud
- [ ] Start gage transmissions (responsibility of HHD Project Team)
- [ ] Load configuration for new HHD instruments
- [ ] Add Precipitation Gages

## Misc
- [ ] Add tables to track vertical and horizontal datums available for a given project
     
- [ ] Load HHD Complete Dataset
