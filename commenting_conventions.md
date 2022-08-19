#   DOXYGEN DOCUMENTATION 

>   FILES

-   `\file` to document a file.

        /*! \file   structcmd.h
            \brief  A Documented file.
            
            Details.
        */

>   DEFINES

-   `\def` to document a #define.

        /*! \def    MAX(a,b)
            \brief  A macro that returns the maximum of \a a and \a b.
        
            Details.
        */
        #define MAX(a, b)

        OR

        #define MAX(a, b)               /*!< A macro that returns the maximum of \a a and \a b. */  

>   STRUCTURES

-   `\struct` to document a C-struct.

        /*! \struct  __deviceInfo
            \brief   A structure that contains all the data for device info
        
            Details.
        */                
        struct __deviceInfo {
            uint8_t serialNo;           /*!< Element that contains serial number of the device. */  
        };



>   UNIONS

-   `\union` to document a union.

        /*! \union  __floatToHex
            \brief  An uninon that contains floating point number in hex format
        
            Details.
        */
        uninon  __floatToHex  {
            float floatNum;                 /*!< floating number that needs to be converted to hex. */
            uint8_t floatToHexArr[4];       /*!< 8bit array for representing hex of float. */
        }



>   ENUMERATIONS

-   `\enum` to document an enumeration type.

        /*! \enum   __monthName
            \brief  An enum that represents all the months name
        
            Details.
        */
        enum __monthName        {
            MONTH_NAME_JANUARY  =   1,      /*!< Value of 1, representing January. */
            MONTH_NAME_FEBRUARY =   2,      /*!< Value of 2, representing February. */
            .....
            MONTH_NAME_DECEMBER =   12,     /*!< Value of 12, representing December. */
        };


>   FUNCTIONS

-   `\fn` to document a function.

        /*! \fn     int read(int fd,char *buf,size_t count)
            \brief  Read bytes from a file descriptor.
            \param  fd      The descriptor to read from.
            \param  buf     The buffer to read into.
            \param  count   The number of bytes to read.
        */        

>   VARIABLES

-   `\var` to document a variable or typedef or enum value.

        /*! \var    int errno
            \brief  Contains the last error code.
        
            \warning Not thread safe!
        */

        OR

        int errno;          /*!< Detailed description after the member */

>   TYPEDEFS

-   `\typedef` to document a type definition.

        /*! \typedef    typedef unsigned int UINT32
            \brief      A type definition for a .
            
            Details.
        */


>  NOTE

-   **FOLLOW NAMING CONVENTION GUIDE ALONG WITH THIS DOCUMENTATION STYLE**   

