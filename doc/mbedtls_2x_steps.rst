.. _mbedtls_2x_steps:

Steps to build MCUX Projects with Mbed TLS 2.x
==============================================

The MCUX projects for MCXN947 can be built with either Mbed TLS 2.x or 3.x.
By default the examples are configured to be built with Mbed TLS 3.x.
To build with Mbed TLS 2.x, follow the below steps,

1. Once the project is opened in MCUXpresso, navigate to project->source->middleware in the project explorer.

2. Right click on mbedtls3x virtual folder, Resource Configurations->Exclude from build->Select all->OK. This will disable mbedtls3x files from build.

3. Right click on mbedtls2x virtual folder, Resource Configurations->Exclude from build->Deselect all->OK. This will enable mbedtls2x files for build.

4. Update the macros in Properties->Settings->Preprocessor. Define EX_SE05X_USE_MBEDTLS2X=1 and remove EX_SE05X_USE_MBEDTLS3X.

5. Change the include paths to point to MBEDTLS_2X in Properties->Settings->Includes. The paths starting with "../../../../../mcxn947-sdk/middleware/mbedtls3x/" should be changed to "../../../../../mcxn947-sdk/middleware/mbedtls/".

6. Update mbedtls config file in  Properties->Settings->Preprocessor. Use MBEDTLS_CONFIG_FILE='"els_pkc_mbedtls_config.h"' and remove MBEDTLS_CONFIG_FILE='"mbedtls3x_config_se05x_auth.h"'

7. Build the project.