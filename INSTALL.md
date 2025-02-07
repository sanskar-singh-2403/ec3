# Installation Instructions

Follow these steps to install and set up the EC3 script:

1. **Clone the Repository**

   Clone the repository to your local machine:

   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Set AWS Profile (Optional)**

   If you need to use a specific AWS profile, you can set it at the start of the script by uncommenting and setting the `AWS_PROFILE` environment variable:

   ```bash
   # Set default AWS profile (uncomment and set your profile if needed)
   # export AWS_PROFILE=<aws-profile>
   ```

3. **Make the Script Executable**

   Make the `ec3.sh` script executable:

   ```bash
   chmod +x ec3.sh
   ```

4. **Move the Script to a Directory in Your PATH**

   Move the `ec3.sh` script to a directory that is in your `PATH`, and rename it to `ec3`:

   ```bash
   sudo mv ec3.sh /usr/local/bin/ec3
   ```

5. **Create the Mapping File**

   Create a mapping file (`~/.ec3rc`) with your instance details:

   ```bash
   vim ~/.ec3rc
   ```

   Add lines in the following format:

   ```
   <keyword>=<instance_id>:<region>
   ```

   Example:

   ```
   webserver=i-1234567890abcdef:us-west-2
   database=i-0987654321fedcba:us-east-1
   ```

6. **Install AWS CLI**

   Ensure you have the AWS CLI installed and configured with the necessary permissions:

   ```bash
   aws configure
   ```

7. **Run the Script**

   You can now run the script to manage your EC2 instances from any directory:

   ```bash
   ec3 <start|stop|list|status> [keyword]
   ```

   Example:

   ```bash
   ec3 start webserver
   ```

That's it! You are now ready to use the EC3 script to manage your AWS EC2 instances.