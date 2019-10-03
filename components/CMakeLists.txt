set(srcs "mjd/mjd.c"
         "mjd_neom8n/mjd_neom8n.c"
         "mjd_neom8n/minmea/minmea.c")

idf_component_register(SRCS "${srcs}"
                    INCLUDE_DIRS "mjd_neom8n/include"
                                 "mjd_neom8n/minmea"
                                 "mjd/include"
                    REQUIRES spi_flash
                             json
                             mbedtls
                             nvs_flash
                    )
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Dtimegm=mktime")