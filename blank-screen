#!/usr/bin/python3

from argparse import ArgumentParser
from os import system

delay = 300
cmd = 'gsettings set org.gnome.desktop.session idle-delay %d'

parser = ArgumentParser()
parser.add_argument("-s", "--seconds", help="Delay in seconds "
                    "(0 to disable, default: 300secs)", type=int)
args = parser.parse_args()

if args.seconds is not None:
    if args.seconds >= 0:
        delay = args.seconds
    else:
        print("The argument should be greater than or equal to 0")
        exit(2)

if delay < 60:
    if delay == 0:
        print("Disabling screen lock...")
    else:
        print("Setting screen lock to %d seconds..."% delay)
else:
    mins = delay/60
    secs = delay % 60
    if secs:
        print("Setting screen lock to %d mins and %d seconds..."%
              (mins,secs))
    else:
        print("Setting screen lock to %d mins..."%mins)

system(cmd%delay)
