
ADD_LIBRARY (persist
	BackingQuery.cc
	BackingStore.cc
	PersistSCM.cc
	StorageNode.cc
)

TARGET_LINK_LIBRARIES(persist
	storage-types
	atomspace
	smob
)

ADD_GUILE_EXTENSION(SCM_CONFIG persist "opencog-ext-path-persist")

INSTALL (TARGETS persist EXPORT AtomSpaceTargets
	DESTINATION "lib${LIB_DIR_SUFFIX}/opencog"
)

INSTALL (FILES
	BackingStore.h
	StorageNode.h
	PersistSCM.h
   DESTINATION "include/opencog/persist/api"
)
