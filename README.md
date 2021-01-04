## OpenCV: Open Source Computer Vision Library

### Resources

* Homepage: <https://opencv.org>
  * Courses: <https://opencv.org/courses>
* Docs: <https://docs.opencv.org/master/>
* Q&A forum: <http://answers.opencv.org>
* Issue tracking: <https://github.com/opencv/opencv/issues>
* Additional OpenCV functionality: <https://github.com/opencv/opencv_contrib> 


### Contributing

Please read the [contribution guidelines](https://github.com/opencv/opencv/wiki/How_to_contribute) before starting work on a pull request.

#### Summary of the guidelines:

* One pull request per issue;
* Choose the right base branch;
* Include tests and documentation;
* Clean up "oops" commits before submitting;
* Follow the [coding style guide](https://github.com/opencv/opencv/wiki/Coding_Style_Guide).

# Download
	
	$ sudo su
 
	$ cd /opt
 
	/opt$ git clone https://github.com/gmarzioz/opencv.git
 
	/opt$ git clone https://github.com/gmarzioz/opencv_contrib.git
	
# Install

	/opt$ cd opencv
 
	/opt/opencv$ mkdir release
 
	/opt/opencv$ cd release

	/opt/opencv/release$ cmake -D BUILD_TIFF=ON -D WITH_CUDA=OFF -D ENABLE_AVX=OFF -D WITH_OPENGL=OFF -D WITH_OPENCL=OFF -D WITH_IPP=OFF -D WITH_TBB=ON -D BUILD_TBB=ON -D WITH_EIGEN=OFF -D WITH_V4L=OFF -D WITH_VTK=OFF -D BUILD_TESTS=OFF -D BUILD_PERF_TESTS=OFF -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D OPENCV_EXTRA_MODULES_PATH=/opt/opencv_contrib/modules /opt/opencv
	/opt/opencv/release$ make -j4

	/opt/opencv/release$ make install

	/opt/opencv/release$ ldconfig
 
	/opt/opencv/release$ exit

	/opt/opencv/release$ cd ~
  
  # Rebuild
  
      rm ../CMakeCache.txt
      
 then rebuild
  
  # Test installation
    $ pkg-config --modversion opencv
    
  # Install traincascade from 3.4.0
  For an error build traincascade from https://github.com/opencv/opencv/archive/3.4.0.tar.gz
  
	sudo mkdir /opt/opencv34
	sudo chown -R $USER /opt/opencv34
	cd /opt/opencv43
	wget https://github.com/opencv/opencv/archive/3.4.0.tar.gz
	tar -xvpf 3.4.0.tar.gz
	cd opencv-3.4.0/
	mkdir build & cd build
	ccmake ..
	cd apps/traincascade
	make
	cd /usr/local/bin/
	sudo ln -s /opt/opencv34/opencv-3.4.0/build/bin/opencv_traincascade
