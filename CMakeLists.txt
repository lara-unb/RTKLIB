cmake_minimum_required(VERSION 3.5)
project( RTKLIB )
set(CTARGET "-DENAGLO -DENAQZS -DENACMP -DENAGAL -DENAIRN -DNFREQ=3 -DSVR_REUSEADDR")
add_definitions(-Wall -O3 -ansi -pedantic -Wno-unused-but-set-variable -DTRACE -g ${CTARGET})

include_directories(${RTKLIB_SOURCE_DIR}/src)

SET(RTKLIB_SRC
	${RTKLIB_SOURCE_DIR}/src/convgpx.c
	${RTKLIB_SOURCE_DIR}/src/convkml.c
	${RTKLIB_SOURCE_DIR}/src/convrnx.c
	${RTKLIB_SOURCE_DIR}/src/datum.c
	${RTKLIB_SOURCE_DIR}/src/download.c
	${RTKLIB_SOURCE_DIR}/src/ephemeris.c
	${RTKLIB_SOURCE_DIR}/src/geoid.c
	${RTKLIB_SOURCE_DIR}/src/gis.c
	${RTKLIB_SOURCE_DIR}/src/ionex.c
	${RTKLIB_SOURCE_DIR}/src/lambda.c
	${RTKLIB_SOURCE_DIR}/src/options.c
	${RTKLIB_SOURCE_DIR}/src/pntpos.c
	${RTKLIB_SOURCE_DIR}/src/postpos.c
	${RTKLIB_SOURCE_DIR}/src/ppp_ar.c
	${RTKLIB_SOURCE_DIR}/src/ppp.c
	${RTKLIB_SOURCE_DIR}/src/ppp_corr.c
	${RTKLIB_SOURCE_DIR}/src/preceph.c
	${RTKLIB_SOURCE_DIR}/src/qzslex.c
	${RTKLIB_SOURCE_DIR}/src/rcvraw.c
	${RTKLIB_SOURCE_DIR}/src/rinex.c
	${RTKLIB_SOURCE_DIR}/src/rtcm2.c
	${RTKLIB_SOURCE_DIR}/src/rtcm3.c
	${RTKLIB_SOURCE_DIR}/src/rtcm3e.c
	${RTKLIB_SOURCE_DIR}/src/rtcm.c
	${RTKLIB_SOURCE_DIR}/src/rtkcmn.c
	${RTKLIB_SOURCE_DIR}/src/rtkpos.c
	${RTKLIB_SOURCE_DIR}/src/rtksvr.c
	${RTKLIB_SOURCE_DIR}/src/sbas.c
	${RTKLIB_SOURCE_DIR}/src/solution.c
	${RTKLIB_SOURCE_DIR}/src/streamsvr.c
	${RTKLIB_SOURCE_DIR}/src/stream.c
	${RTKLIB_SOURCE_DIR}/src/tides.c
	${RTKLIB_SOURCE_DIR}/src/tle.c
	${RTKLIB_SOURCE_DIR}/src/rcv/binex.c
	${RTKLIB_SOURCE_DIR}/src/rcv/cmr.c
	${RTKLIB_SOURCE_DIR}/src/rcv/crescent.c
	${RTKLIB_SOURCE_DIR}/src/rcv/gw10.c
	${RTKLIB_SOURCE_DIR}/src/rcv/javad.c
	${RTKLIB_SOURCE_DIR}/src/rcv/novatel.c
	${RTKLIB_SOURCE_DIR}/src/rcv/nvs.c
	${RTKLIB_SOURCE_DIR}/src/rcv/rcvlex.c
	${RTKLIB_SOURCE_DIR}/src/rcv/rt17.c
	${RTKLIB_SOURCE_DIR}/src/rcv/septentrio.c
	${RTKLIB_SOURCE_DIR}/src/rcv/skytraq.c
	${RTKLIB_SOURCE_DIR}/src/rcv/ss2.c
	${RTKLIB_SOURCE_DIR}/src/rcv/tersus.c
	${RTKLIB_SOURCE_DIR}/src/rcv/ublox.c
	)

add_library(rtklib
	${RTKLIB_SRC}
)
# file(MAKE_DIRECTORY "bin")
# set(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)
# add_executable(RTKLIB ${RTKLIB_SRC})
# target_link_libraries( RTKLIB ${OpenCV_LIBS})
