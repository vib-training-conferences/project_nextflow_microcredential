# Project Nextflow Microcredential

Nextflow project to be developed for the micro-credential VIB/UGent - Reproducble analysis

In this project you will create a Nextflow pipeline based on some data analysis from your research field or following an example provided by the lecturers.

This project should adhere to the following requirements to succeed:

# Requirements Nextflow project

The following table lists the basic requirements to pass the Nextflow project. If your project meets all these requirements you will pass the project.

| Requirement                                                                                                                                                                                                                                                        | Grade |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----- |
| Should be on Github (Please add the link to [`projects.md`](projects.md))                                                                                                                                                                                          | /1    |
| Docker and Apptainer compatibility of all modules. See the [docs](https://www.nextflow.io/docs/latest/container.html) for more information.                                                                                                                        | /1    |
| Should contain at least 3 modules from tools that weren't covered during the training                                                                                                                                                                              | /1    |
| At least 1 module should contain a custom script                                                                                                                                                                                                                   | /1    |
| At least 1 module should be made with an existing tool (if possible for your field)                                                                                                                                                                                | /1    |
| Should contain at least 1 config profile                                                                                                                                                                                                                           | /1    |
| Should not need any prior setup (the pipeline should work out-of-the-box on the infrastructure used during the training) with minimal test data                                                                                                                    | /2    |
| Should output relevant files to an output directory                                                                                                                                                                                                                | /1    |
| Should contain at least 3 different [operators](https://www.nextflow.io/docs/latest/reference/operator.html#operators)                                                                                                                                             | /1    |
| Should be documnted with a README file containing at least: a description of the pipeline, instructions how to run the pipeline and an explanation of the input and output files. Extra information and well written information can result in an extra point here | /2    |

# Nice to haves

These requirements are optional but can give you extra points when implemented in your project:

| Nice to have                                                                    | Grade |
| ------------------------------------------------------------------------------- | ----- |
| Process resources should be managed in the nextflow.config using process labels | /1    |
| Follow the nf-core best practice guidelines                                     | /1    |
| The pipeline contains a subworkflow                                             | /1    |

# Good to know

Here's a list of gotchas and tips to help you create a good project:

1. Make sure that your pipeline can be run using the `nextflow run <git-username>/<repository>` command without any prior setup. Adding this command with the needed arguments in your README file can help us run your pipeline even faster. Ask a colleague to test this for you so you are sure it works for everyone.
2. Make sure your data is reachable from the HPC, by either adding it to the pipeline repository or by hosting these files in any other way that's publicly accessible. Keep in mind that all files present in the repository will also be downloaded when running the pipeline, which is fine for this project, but might not be ideal for later projects you create.
3. Add comments to your code explaining what each part does. This will help us understand your reasoning and will make it easier to give you points for the requirements.
4. Make sure your code is properly formatted and indented. The `nextflow lint -format` command can help you with this. (available in Nextflow version 25.04.0 and higher)
5. If analysis in your field is more scripting based, and existing tools are rarely used, it is acceptable to have 3 modules with custom scripts instead.

# Remarks Q2 2026
Due to security issues, VSC Ugent has temporarily blocked the building of apptainer images on the cluster. Due to this, if you specify a docker container for your process, Nextflow will trow an error after pulling the docker container while trying to convert it to an apptainer image. We propose 2 solutions to this problem, please choose one of them:
1. Instead of specifying a docker container, specify an apptainer image (hosted on a remote repository) directly in the process `container` directive.
2. Convert the docker container to an apptainer image on a system where this is allowed. When this is done, copy the SIF image to this course's shared folder on the VSC `/data/gent/courses/2025/vibrepdata_EXT003/shared/apptainer_cache/`

If you cannot get this to work, make sure the pipeline at least works on a linux environment with docker and nextflow installed.
