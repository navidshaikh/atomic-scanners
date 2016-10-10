# atomic-scanners
Atomic scanners for scanning containers and images.

A set of atomic scanners devised for extracting data about containers and images.
Each scanner extracts a particular type of data. The idea here is to build a
stack of lightweight atomic scanners and provide mechanism to plug into
different infrastructure. An administrator can choose particular set of scanners,
among the scanners stack and run on the given deployment, registry, etc.


## Scanners:
 - [scanner-rpm-verify](scanner-rpm-verify/)
 - [pipeline-scanner](pipeline-scanner/)

## Integration:
iIn order to plug the atomic scanners stack into different tooling and services,
integration points need to be provided.

### Integration with [Container Pipeline Service](https://github.com/CentOS/container-pipeline-service):
CientOS Community Container Pipeline(cccp) is a process, to provide any opensource developer, a platform for containerising their application(s). This process builds the application(s) from any arbitary git repository/repositories, package the built application along with its runtime in a container image, tests the image with help of test script and delivers to a publicly available registry. A user can anytime pull the tested image from that registry.

An image under build process passes through different build phases, once the image is built, it passes through a testing phase.
Atomic scanners stack can be plugged in the testing phase, where it extracts data about the built images. The data generated can also be stored for records.


