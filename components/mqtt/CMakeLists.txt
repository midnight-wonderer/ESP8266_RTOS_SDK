idf_component_register(SRCS "esp-mqtt/mqtt_client.c"
                            "esp-mqtt/lib/mqtt_msg.c"
                            "esp-mqtt/lib/mqtt_outbox.c"
                            "esp-mqtt/lib/platform_esp32_idf.c"
                    INCLUDE_DIRS esp-mqtt/include
                    PRIV_INCLUDE_DIRS "esp-mqtt/lib/include"
                    REQUIRES lwip http_parser mbedtls tcp_transport)

target_compile_definitions(${COMPONENT_LIB} PUBLIC -DMQTT_SUPPORTED_FEATURE_WS_SUBPROTOCOL -DMQTT_SUPPORTED_FEATURE_TRANSPORT_ERR_REPORTING)
