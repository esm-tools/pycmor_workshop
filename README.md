# Pycmor Workshop

Clone this repository to get access to the slides and practice problems:

```
$ git clone https://github.com/esm-tools/pycmor_workshop.git
$ cd pycmor_workshop
$ mkdir work
```

Make a folder to work in, for example:
```
$ cd work
```

During the live workshop, you'll be able to use the QOS `--qos=training` in DKRZ's HPC, to gain priority in the slurm queue. To benefit from this make sure you add this to your `salloc` or `sbatch` commands, or to the `#SBATCH` headers of the scripts.

---

## Outline

### 1. Intro
  * Workshop intro - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/aims_outline.pdf), [Video](https://nextcloud.awi.de/s/KswDLXAYfiWeeQS)
    * Aims
    * Outline
  * Pycmor - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/pymor_intro.pdf), [Video](https://nextcloud.awi.de/s/9wRE2YaweAX98bp)
    * What is Pycmor?
    * Main Pycmor features
  * Demo: [pycmor cli](https://github.com/esm-tools/pycmor_workshop/blob/main/demos/cli.md), [Video](https://nextcloud.awi.de/s/TLcSQkpos66i33n)
  * Time to resolve installation problems @pgierz
    * Have you installed Pycmor inside a conda environment named `pycmor` already?
    * Can you run `pycmor --help` and other commands?
    * Maybe you need to upgrade (`pip install --upgrade py-cmor[dev,fesom]`)
### 2. Pycmor syntax
  * Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/yaml_syntax.pdf), [Video](https://nextcloud.awi.de/s/AWCYpscWwzozxRW)
  * Exercise: [Running a basic pycmor process (text and solutions)](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/basic.md), [Video](https://nextcloud.awi.de/s/gxetpicnqBNdsiK)
### 3. Features
#### 3.1. Units (`module_units` and `cmor_units`)
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/units.pdf), [Video](https://nextcloud.awi.de/s/NpfBNQ5wBo2GMZx)
* Exercise: [Unit conversion (text and solutions)](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/unit_conversion.md), [Video](https://nextcloud.awi.de/s/bzmkrYqRfDW3ZF3)
#### 3.2. Time span for output files (`file_timespan`)
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/file_timespan.pdf), [Video](https://nextcloud.awi.de/s/Gtn3ezrpWTnR4yj)
* Exercise: [File timespan (text and solutions)](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/file_timespan.md), [Video](https://nextcloud.awi.de/s/oTTLZW6PpgZxos8)
#### 3.3. Time averages
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/timeaverage.pdf), [Video](https://nextcloud.awi.de/s/qK8LNg8HoPEBCXb)
* Exercise: [Temporal frequency](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/temporal_frequency.md), [Video](https://nextcloud.awi.de/s/Fw2fsxXAoKG2GS9)
#### 3.4. Adjusting time stamps of steps
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/timeaverage.pdf), [Video](https://nextcloud.awi.de/s/rmfD7sZbzTfZNf4)
* Exercise: [Adjust timestamp](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/adjust_timestamp.md), [Video](https://nextcloud.awi.de/s/xYRrwDMweci7wan)
#### 3.5. Control computing resources
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/compute_resources.pdf), [Video](https://nextcloud.awi.de/s/xdWj32zcXNYBygi)
* Exercise: [Costumizing your compute resources](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/compute-resources.md), [Video](https://nextcloud.awi.de/s/Ywws9FHHTPdmLCd)
#### 3.6. Pipelines and custom steps
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/pipelines_and_custom_steps.pdf), [Video](https://nextcloud.awi.de/s/KkNaoXWESE2zTiM)
* Exercise: [Add a custom step in the pipeline](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/custom-step.md), [Video](https://nextcloud.awi.de/s/qbzS5MPopt9nBnJ)
#### 3.7. Combining model output variables
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/combining_variables.pdf)
* Exercise: [Using aux files](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/aux_files.md)
#### 3.8. PyFESOM
* Presentation - [Slides](https://github.com/esm-tools/pycmor_workshop/blob/main/pdfs/pyfesom2_features.pdf)
* Exercise: [Using pyfesom2 with pycmor](https://github.com/esm-tools/pycmor_workshop/blob/main/exercises/pyfesom2_exercises.md)
### 4. Try Pycmor with your data
### 5. Close the workshop

---

## Install Pycmor

As the data to run the exercises lives on Levante,(DKRZ), we need to setup the Pycmor package on Levante.

The installation is done in 2 steps:

  1. Create a virtual environment
  2. Install Pycmor

### Create a virtual environment

**Note:** the exercises assume you have a `pycmor` conda environment, so make sure when you create the environment that its name matches that.

```bash
module load python3
eval "$(conda shell.bash hook)"      # Init conda without the need to add extra lines to ~/.bashrc
conda create -n pycmor python=3.10    # Create a conda environment named pycmor
```

### Install Pycmor

```bash
conda activate pycmor
pip install --isolated py-cmor[dev,fesom]
```

You can then check the Pycmor works by running:

```bash
pycmor --version
pycmor --help
```

For additional information, check out the following links

- Creating Virtual environments on Levante: [Python environment locations](https://docs.dkrz.de/blog/2021/conda_path.html#python-environment-locations).
- Installing Pycmor: [Pycmor documentation](https://pymor.readthedocs.io/en/latest/installation.html).


## Pycmor workshop repository

The Pycmor workshop repository contains scripts to run the exercises.

```bash
work="/work/$(id -gn)/$USER"
echo "work directory: $work"
cd $work
git clone https://github.com/esm-tools/pycmor_workshop.git
cd pycmor_workshop
```

## Get the example data

This workshop is designed for ease-of-use if you are working on DKRZ's Levante system. You can access all of the test data here:

```
/work/ab0995/a270243/pycmor_workshop/exercises/data
```

If you want to be able to see the files as part of your own repository, you can make a link

```bash
pwd  # You should be in the root of the repository (`/work/$PROJECT/$USER/pycmor_workshop`)
ln -sv /work/ab0995/a270243/pycmor_workshop/exercises/data ./exercises/data
```

Alternatively, if you would like to use synthetic data made up of random numbers, but with realistic metadata, dimensions,
and attributes, you can generate some. Make sure you are in the same Python environment as `pycmor` is installed for this:
```bash
make fake-data
ln -sv ./fake-data ./exercises/data
```
