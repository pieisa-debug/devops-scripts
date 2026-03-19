#!/usr/bin/env python3

"""
This is a collection of devops scripts for automating various tasks.
"""

import argparse
import os
import subprocess

def run_script(script_name):
    """
    Run a script with the given name.

    Args:
        script_name (str): The name of the script to run.

    Returns:
        int: The exit code of the script.
    """
    script_path = os.path.join(os.path.dirname(__file__), script_name)
    if not os.path.exists(script_path):
        raise FileNotFoundError(f"Script '{script_name}' not found")
    return subprocess.run([script_path]).returncode

def main():
    parser = argparse.ArgumentParser(description="Run devops scripts")
    parser.add_argument("script", help="The name of the script to run")
    args = parser.parse_args()

    try:
        exit_code = run_script(args.script)
        if exit_code!= 0:
            print(f"Script '{args.script}' failed with exit code {exit_code}")
        else:
            print(f"Script '{args.script}' ran successfully")
    except Exception as e:
        print(f"Error running script: {e}")

if __name__ == "__main__":
    main()