# HHD Burndown List: Soft Delivery (July 29, 2020)

## Data Explorer (Dashboard)

### Map
  * Display projects on map
  * Display instruments on map
 
### Plots
  * Timeseries Plots
    * Show rainfall on separate plot window
    * Show Pool/Tail on plot
  * Correlation Plots
  * API: Transform raw measurements into elevation
    What is the common parameter? `elevation-water`
  
### API Endpoint for fetching many timeseries
  
  `<POST> /instrumentation/explorer?parameter_id=<uuid>`
  
  * Client to Send JSON: Instrument IDs `[ <uuid>, <uuid>, ]`
  
  * Server to Send JSON:
  
    ```
    { <instrument_id>: [
        { timeseries_id: <uuid4>,
          parameter_id : <uuid4>,
          unit_id      : <uuid4>,
          measurements : [
          { time: time, value: <value> },
          { time: time, value: <value> },
          { time: time, value: <value> }
          ]
        },
        { timeseries_id: ...
        }
      ]
    }
    ```
    
    **After some work, maybe we go even leaner on the JSON structure? Something like this?**
    ```
    { <instrument_id>: {
        <timeseries_id>: [
          { time: time, value: <value> },
          { time: time, value: <value> },
          { time: time, value: <value> }
        ],
        <timeseries_id>: [
          { time: time, value: <value> },
          { time: time, value: <value> },
          { time: time, value: <value> }
        ]
      },
      <instrument_id>: {...
      }
    }    
    ```

## Data Import/Export
   * Import Instruments
     * Import validation: Check names to be uploaded via POST
       * Instrument Names: POST array of names, return collisions
         If no collisions, return []. Otherwise return list of colliding names
       * Optional Fields: 
     * Allow multiple coordinate systems. Must supply an EPSG Code.
   * Import Timeseries Measurements
     * Note: Timeseries must exist to upload measurements.
     * Will have button to create new timeseries in uploader.
   * Export Instruments (csv)
   * Export Timeseries  (csv)

## Timeseries text for plot annotations
   * Instrument Notes
   * Thresholds `{ type: above (below, at), name: "Action Stage"}` or similar? (if we have time)

## Nail-down Roles
        
   * Project Level Privileges
     * ProjectAdmin
       Can Manage Instruments, Instrument Groups
       Delete capability
     * ProjectMember
       Can Add Timeseries Data
   * Application Level Priviliges
     * ApplicationAdmin:
       Can modify user roles
       Can create projects

   * isLoggedIn : No roles
   * Anon       : Not Logged In (general public)
   
## Real Time Data Acquisition

   * Get it running in the cloud
   * Start transmissions (responsibility of HHD Project Team)
   * Load configuration for new HHD instruments (waiting on HHD Project Team)
   * Precipitation Data

## Misc
   * Add tables to track vertical and horizontal datums available for a given project
     
## Load HHD Complete Dataset
   * More discussion required here
