.PHONY: all clean doc

all: registration_protoc_middleman collab_protoc_middleman

doc: doc/registration.md doc/registration.html doc/collaboration.md doc/collaboration.html

clean:
	rm registration_protoc_middleman collab_protoc_middleman
	rm python/registration_pb2.py src/registration.pb.cc src/registration.pb.h
	rm python/collaboration_pb2.py src/collaboration.pb.cc src/collaboration.pb.h
	rm doc/registration.md doc/registration.html doc/collaboration.md doc/collaboration.html

registration_protoc_middleman: registration.proto
	protoc --cpp_out=src --python_out=python registration.proto
	@touch registration_protoc_middleman

doc/registration.md: registration.proto
	protoc --doc_out=markdown,registration.md:doc registration.proto

doc/registration.html: registration.proto
	protoc --doc_out=html,registration.html:doc registration.proto

collab_protoc_middleman: collaboration.proto
	protoc --cpp_out=src --python_out=python collaboration.proto
	@touch collab_protoc_middleman

doc/collaboration.md: collaboration.proto
	protoc --doc_out=markdown,collaboration.md:doc collaboration.proto

doc/collaboration.html: collaboration.proto
	protoc --doc_out=html,collaboration.html:doc collaboration.proto
