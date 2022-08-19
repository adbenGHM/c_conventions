# NAMING CONVENTIONS FOR FIRMWARE


>   FILE NAME

1.  All lower case with all the words seperated by underscore.

    Example:   `example_file_name.x` , .x = file extention

>   MACROS

1.  All capital case with words separated by an Underscore. 
2.  Must be prefixed by the file name.

    Example: Considering file name as, `app_sensor.h`,

    Macro Name: `APP_SENSOR_DEVICE_ADDR`

>   VARIABLES

1.  Every variable name must be self-explanatory.
2.	Variable name must be in lower camel case.

    Local Variable:   `lowerCamelCase`  *(local normal variable)*

3.  Pointer type variables must be in camel case prefixed by *p*.

    Pointer Variable:   `int pSampleVar`  *(local pointer variable)*

4.  Global variables that are declared inside a source file must be declared *static*.
    Global static variable must be prefixed by *g*.

    Global Variable:    `static int gSampleVar` *(global normal variable)*

    Global Pointer Variable:    `static int *pgSampleVar` *(global pointer variable)*

6.  Constant variables should be written in capital case.
    Words should be separated by an underscore.

    Constant Variable:  `const int SIMPLE_VAR`  *(constant variable)*

7.  All the variables that are declared in header files (with global scope),
    must be preceded by file name with underscore sperated by file name and variable name.

    Considering file name as, `app_sensor.h`,

    Header file global variable:    `int app_sensor_dataReadyFlag`  *(global header file variable)*

    Header file pointer global variable:    `int *app_sensor_pDataReadyFlag`  *(global header file variable)*

8.  Variable name should never start with a verb.

    Example:    
    `runDevice` **WRONG**

    `isDeviceRunning`   **RIGHT**  


>   TYPEDEFS

1.  Typedef name must be in upper camel case.



2.  Typedef name must be prefixed by the file name if not declared static (or under a src scope only).
3.  Typedef must be terminated with *_t*
4.  Typedef tag (if used) should be same as typedef without the suffixed *_t*.

    Example: File name `app_sensor.c`

            typedef enum app_sensor_dataFetchState        {
                APP_SENSOR_DATA_FETCH_STATE_INIT        =   1,
                APP_SENSOR_DATA_FETCH_STATE_FETCH       =   2,
                APP_SENSOR_DATA_FETCH_STATE_DEINIT      =   3    
            }app_sensor_dataFetchState_t;   


            typedef struct app_sensor_devInfo     {
                int deviceId;
                int manufactureDate;
                float serialNum;
            }app_sensor_devInfo_t;
5.  Typedef variable name should not be same as typedef name or typedef tag

    Example:
    
            typedef struct exampleStruct{
    
            }exampleStruct_t;
    
            exampleStruct_t exampleStruct   **WRONG**
    
    
    
    Now if these typedef variables are decalared anywhere, it must follow the variable naming conventions.

    Example:

    `app_sensor_dataFetchState_t sampleVar`                     *(local normal variable)*

    `app_sensor_dataFetchState_t *pSampleVar`                   *(local pointer variable)*

    `app_sensor_dataFetchState_t gSampleVar`                    *(global normal variable)*  

    `app_sensor_dataFetchState_t *pgSampleVar`                  *(global pointer variable)*

    `app_sensor_dataFetchState_t app_sensor_sampleVar`          *(point 2 of **TYPEDEFS**)*

    `app_sensor_dataFetchState_t *app_sensor_pSampleVar`        *(point 2 of **TYPEDEFS**)*

>   PRIVATE FUNCTIONS

1.  These functions should be strictly defined and declared in the source file only.
2.  Function name must contain a verb.
3.  Function name must be in upper camel case (Pascal Case)
    
    Example:    `UpperCamelCase`

4.  Must be declared as static.
5.  File name prefixing should not be used.    

>   PUBLIC FUNCTIONS

1.  Function name must contain a verb, preferably start with verb.
2.  Function name must be in upper camel case (Pascal Case)

    Example:    `UpperCamelCase`

3.  Must be prefixed with file name.
4.  File name and function name should be seperated using an underscore.
5.  Function name might be prefixed with their return type.`*`.  

    -   Type uint32_t: use prefix *ul*.
    -   Type uint16_t: use prefix *us*.
    -   Type uint8_t: use prefix *uc*.
    -   Type void: use prefix *v*.
    -   Any other return type: use prefix *x*.
    -   Type pointer: use prefix *p* in addition to the above return type.
  

    Example:    file name `app_sensor.h`

    `app_sensor_GetSensorData()`


>   ENUMERATIONS

1.  Enum elements must be under a typedef.
2.	Typedef naming conventions must be strictly followed.
3.	Enum elements must be all capital case. 
4.	Enum elements must be followed by the enum typedef name.

    Example: File name `app_sensor.c`

            typedef enum app_sensor_dataFetchState        {
                APP_SENSOR_DATA_FETCH_STATE_INIT        =   1,
                APP_SENSOR_DATA_FETCH_STATE_FETCH       =   2,
                APP_SENSOR_DATA_FETCH_STATE_DEINIT      =   3    
            }app_sensor_dataFetchState_t;   


>   NOTES

`*` **NOT MANDATORY**



