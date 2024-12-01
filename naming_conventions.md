## <u>**C NAMING CONVENTIONS**</u>
&nbsp;
>   ### **TABLE OF CONTENTS**
 1. [File name](#file-name)
 2. [Macros](#macros)
 3. [Variables](#variables)
 4. [Typedefs](#typedefs)
 5. [Private Functions](#private-functions)
 6. [Public Functions](#public-functions)
 7. [Enumarations](#enumerations)
 8. [Generic](#generic)
 9. [Notes](#notes)

&nbsp;

>  ### **FILE NAME**

1.  All lower case with all the words seperated by underscore.

    <u>**Example :**</u>   `example_file_name.x` , .x = file extention

>  ### **MACROS**

1.  Must be prefixed by filename
2.  All capital case with words separated by an Underscore. 
3.  Must be prefixed by the file name.

    <u>**Example :**</u> Considering file name as, `app_sensor.h`,

    Macro Name: `app_sensor_DEVICE_ADDR`

>  ### **VARIABLES**

1.  Every variable name must be self-explanatory.
2.	Variable name must be in lower camel case.
    
    <u>**Example :**</u>

    Local Variable:   `lowerCamelCase`  *(local normal variable)*

3.  Pointer type variables must be in camel case prefixed by *p*.

    <u>**Example :**</u>

    Pointer Variable:   `int pSampleVar`  *(local pointer variable)*

4.  Global variables that are declared inside a source file must be declared *static*.

    <u>**Example :**</u>
    
    Global static variable must be prefixed by *g*.

    Global Variable:    `static int gSampleVar` *(global normal variable)*

    Global Pointer Variable:    `static int *pgSampleVar` *(global pointer variable)*

6.  Constant variables should be written in capital case.
    Words should be separated by an underscore.

    <u>**Example :**</u>

    Constant Variable:  `const int SIMPLE_VAR`  *(constant variable)*

7.  All the variables that are declared in header files (with global scope),
    must be preceded by file name with underscore sperated by file name and variable name.

    <u>**Example :**</u>

    Considering file name as, `app_sensor.h`,

    Header file global variable:    `int app_sensor_dataReadyFlag`  *(global header file variable)*

    Header file pointer global variable:    `int *app_sensor_pDataReadyFlag`  *(global header file variable)*
8.  All array name must have resonable suffix or prefix , like ***arr***, ***table***,***matrix*** to identify as array for example

    <u>**Example :**</u>
    
    `int numbers[]`      **WRONG**

    `int numbersArr[]`   **RIGHT**

    `int arrOfNumbers[]` **RIGHT**

9. Char array or pointer intended to be used as ASCII string must be suffixed or prefixed with ***string*** or ***str***

    <u>**Example :**</u>

    `char strSample[]`

    `char smapleString[]`

    `char *pSampleStr`

9.  Verbs as the starting of variable name should be avoided 

    <u>**Example :**</u>  

    `runningDevice`     **Not preferred**

    `isDeviceRunning`   **Preferred**  


>  ### **TYPEDEFS**

1.  Typedef name must be in lower camel case.
2.  Typedef name must be prefixed by the file name if not declared static (or under a src scope only).
3.  Typedef must be terminated with *_t*
4.  Typedef tag (if used) should be same as typedef with the `tag` word appended.

    <u>**Example :**</u>

    for file name `app_sensor.c`

            typedef struct app_sensor_tagDevInfo     {
                int deviceId;
                int manufactureDate;
                float serialNum;
            }app_sensor_devInfo_t;

    &nbsp;


    Now if these typedef variables are decalared anywhere, it must follow the variable naming conventions.

    <u>**Example :**</u>

    `app_sensor_dataFetchState_t sampleVar`                     *(local normal variable)*

    `app_sensor_dataFetchState_t *pSampleVar`                   *(local pointer variable)*

    `app_sensor_dataFetchState_t gSampleVar`                    *(global normal variable)*  

    `app_sensor_dataFetchState_t *pgSampleVar`                  *(global pointer variable)*

    `app_sensor_dataFetchState_t app_sensor_sampleVar`          *(point 2 of **TYPEDEFS**)*

    `app_sensor_dataFetchState_t *app_sensor_pSampleVar`        *(point 2 of **TYPEDEFS**)*

>  ### **PRIVATE FUNCTIONS**

1.  These functions should be strictly defined and declared in the source file only.
2.  Function name must contain a verb, preferably start with verb.
3.  Function name must be in upper camel case (Pascal Case)
    
    <u>**Example :**</u>    `UpperCamelCase`

4.  Must be declared as static.
5.  File name prefixing should not be used.    

>  ### **PUBLIC FUNCTIONS**

1.  Function name must contain a verb, preferably start with verb.
2.  Function name must be in upper camel case (Pascal Case)
3.  Must be prefixed with file name.
4.  File name and function name should be seperated using an underscore.

    <u>**Example :**</u>  
    
    A function inside a file `app_sensor.h` can be `app_sensor_GetSensorData()`
5.  Function name might be suffixed with their return type.`*`.  

    -   Type uint32_t: use suffix *`_ul`*.
    -   Type uint16_t: use suffix *`_us`*.
    -   Type uint8_t: use suffix *`_uc`*.
    -   Type void: use suffix *`_v`*.
    -   Any other return type: use suffix *`_x`*.
    -   Type pointer: use suffix *`_p`* in addition to the above return type.
  

>  ### **ENUMERATIONS**

1. Must be prefixed by file name in small
2.	Typedef naming conventions must be strictly followed.
3.	Enum elements must be all capital case. 
4.	Enum elements must be followed by the enum typedef name, if its a typedef.
5.	Enum typedef name must start with e 
6.	enum elements name must start with e after the file name

    <u>**Example :**</u> 
    
    For file name `app_sensor.c`

            typedef enum app_sensor_tagDataFetchState        {
                app_sensor_eDATA_FETCH_STATE_INIT        =   1,
                app_sensor_eDATA_FETCH_STATE_FETCH       =   2,
                app_sensor_eDATA_FETCH_STATE_DEINIT      =   3    
            }app_sensor_eDataFetchState_t;   

>  ### **GENERIC**

This are to be followed for every namings, unless specified

1. Never use `__ or _` **prefix** for variables/functions/macros/types. This is reserved for C language itself 


>  ### **NOTES**

`*` **NOT MANDATORY**



