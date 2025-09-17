# CloudSim
Perfect! Let’s go step by step so you can clone a CloudSim GitHub project into Eclipse and run something like SJF scheduling, with all the details explained.

Step 1: Install Prerequisites

Before doing anything:

Make sure Java JDK is installed (Java 8 or 11 is preferred for CloudSim).

Check by running in terminal:

java -version


Eclipse IDE installed (Eclipse IDE for Java Developers is enough).

Step 2: Clone the GitHub Repo

You can clone directly inside Eclipse or via Git command line.

Option A: Eclipse

File → Import → Git → Projects from Git → Clone URI

Paste your GitHub repo URL.

Click Next → Next → Finish.

Choose Import as Java Project when Eclipse asks.

Option B: Git CLI
git clone https://github.com/username/your-cloudsim-project.git


Then in Eclipse:

File → Import → Existing Projects into Workspace → Select root directory → Finish

Step 3: Add CloudSim Libraries

CloudSim is not part of standard Java. You need its JARs.

Download CloudSim:

Official GitHub: CloudSim

Or download a prebuilt jar (e.g., cloudsim-4.0.jar)

Add JARs in Eclipse:

Right-click project → Properties → Java Build Path → Libraries → Add External JARs

Select:

cloudsim-x.x.jar

Any dependency JARs (cloudsim-examples.jar if available)

Click Apply and Close.

Step 4: Check Project Structure

Eclipse requires your files to be in the right folder matching the package:

Example:

package org.cloudbus.cloudsim.examples;

public class SJFExample {
    public static void main(String[] args) {
        // SJF scheduling simulation code
    }
}


Folder structure must be:

src/org/cloudbus/cloudsim/examples/SJFExample.java

Step 5: Run the Simulation

In Eclipse, find the main class with public static void main(String[] args).

Example: SJFExample.java

Right-click → Run As → Java Application

Look at the Console. You should see simulation logs like:

Cloudlet 1 completed
Cloudlet 2 completed
Average turnaround time: ...

Step 6: Common Errors and Fixes
Error	Cause	Fix
package org.cloudbus.cloudsim.core does not exist	CloudSim JAR not in build path	Add JAR as explained in Step 3
cannot find symbol	Wrong import/package mismatch	Check folder structure matches package
NoClassDefFoundError	Using classes not in JAR	Ensure all CloudSim dependencies are added
Step 7: Modifying SJF Scheduling

Open the main class for SJF.

Adjust:

Number of VMs

Number of Cloudlets

Length / Processing time of Cloudlets

Save → Run again.
You will see updated results in the console.

Extra Tips

Start with CloudSim Examples first (they have RoundRobin, FCFS, SJF).

Once examples run fine, move to your custom project.

Always ensure JAR version matches the code (CloudSim 4.0 code won’t work with 3.x JAR).
