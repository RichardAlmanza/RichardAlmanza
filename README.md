# Epam AWS Fundamentals Task

- [Website on AWS](http://web.richard-adolfo-vega-almanza.s3-website-us-east-1.amazonaws.com/)
- [Website on GitHub Pages](https://www.richardalmanza.com/)
- [Repository epam-aws branch](https://github.com/RichardAlmanza/RichardAlmanza/tree/epam-aws)

## Content

- [Epam AWS Fundamentals Task](#epam-aws-fundamentals-task)
  - [Content](#content)
  - [Create Bucket S3](#create-bucket-s3)
  - [Create IAM user for GitHub Actions](#create-iam-user-for-github-actions)
  - [Create access key for IAM User](#create-access-key-for-iam-user)
  - [Setting the secrets up in the GitHub repository](#setting-the-secrets-up-in-the-github-repository)
  - [GitHub repository changes](#github-repository-changes)
  - [Static website hosting - S3](#static-website-hosting---s3)

## Create Bucket S3

1. **AWS Console > S3 > Create Bucket**
    <details>
    <summary>Create Bucket</summary>

    ![Create Bucket Button](images/create-bucket/1.png)

    </details>
2. **General configuration** card
   1. Select **Bucket type > General Purpose**
   2. Fill the **Bucket name** field `web.richard-adolfo-vega-almanza`
   <details>
    <summary><b>General configuration</b> card</summary>

    ![General configuration Setting](images/create-bucket/2.png)

    </details>

3. **Object Ownership** card
   1. Select **ACLs enabled**
   2. Select **Object Ownership > Bucket owner preferred**
   <details>
    <summary><b>Object Ownership</b> card</summary>

    ![Object Ownership Setting](images/create-bucket/3.png)

    </details>

4. **Block Public Access settings for this bucket** card
   1. Deselect/Clear **Block all public access**
   2. Select **I acknowledge that the current settings might result in this bucket and the objects within becoming public** in the warning message at the card's bottom
   <details>
    <summary><b>Block Public Access settings for this bucket</b> card</summary>

    ![Block Public Access settings for this bucket Setting](images/create-bucket/4.png)

    </details>

5. **Bucket Versioning** card
   1. Leave it **Bucket Versioning > Disable**, the git repository already manage a history
   <details>
    <summary><b>Bucket Versioning</b> card</summary>

    ![Bucket Versioning Setting](images/create-bucket/5.png)

    </details>

6. **Tags - optional** card
   1. **Add tag**
      * Key `env`
      * Value `temp`
   <details>
    <summary><b>Tags - optional</b> card</summary>

    ![Tags - optional Setting](images/create-bucket/6.png)

    </details>

7. **Create Bucket**
   1. Leave the **Default encryption** card as default
   2. leave the **Advanced settings** options as default
   3. Click the **Create bucket** button
   <details>
    <summary>Create bucket</summary>

    ![final step](images/create-bucket/7.png)

    </details>

## Create IAM user for GitHub Actions

1. **IAM > Users > Create User**
   <details>
    <summary><b>Create User</b></summary>

    ![Create Iam User](images/create-iam-user/1.png)

    </details>

2. **User details** card
   1. Fill the **User name** field, `github_actions` (in the image is `github_user` but I changed it)
   2. Leave deselected **Provide user access to the AWS Management Console - optional**
   3. Click the **Next** button
   <details>
    <summary><b>User details</b> card</summary>

    ![Username](images/create-iam-user/2.png)

    </details>

3. **Set permissions** Section
   1. Select **Permission options > Add user to group**
   2. Click **User groups > Create group**
   <details>
    <summary><b>set permissions</b> Section</summary>

    ![creating user group](images/create-iam-user/3.png)

    </details>

4. **Create user group** popup
   1. Fill the  **User group name** field, `S3WriteOnly-web.richard-adolfo-vega-almanza`
   2. Click **Create Policy** Bbtton
   <details>
    <summary><b>Create user group</b> popup</summary>

    ![User group name](images/create-iam-user/4.png)

    </details>

5. **Policy editor** card
   1. Click **Policy editor > JSON**
   <details>
    <summary><b>Policy editor</b> card</summary>

    ![Policy editor](images/create-iam-user/5.png)

    </details>

6. **Policy editor** card
   1. Paste the following policy
   2. Click **Next** button

    <details>
        <summary><b>IAM POLICY</b></summary>
    <pre>
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "VisualEditor0",
                "Effect": "Allow",
                "Action": [
                    "s3:PutObject",
                    "s3:ListBucket",
                    "s3:DeleteObject",
                    "s3:PutObjectAcl"
                ],
                "Resource": [
                    "arn:aws:s3:::web.richard-adolfo-vega-almanza/*",
                    "arn:aws:s3:::web.richard-adolfo-vega-almanza"
                ]
            }
        ]
    }
    <code>
    </details>

   <details>
    <summary><b>Policy editor</b></summary>

    ![Policy editor](images/create-iam-user/6.png)

    </details>

7. **Policy details** card
   1. Fill **Policy name** field, `PublishObjectsS3-web.richard-adolfo-vega-almanza`
   2. Fill **Description - optional** field, `Permision mainly for pipelines that will upload the static web`
   3. Scroll down to the **Add tags - optional** card

   <details>
    <summary><b>Policy editor</b> card</summary>

    ![Policy name and description](images/create-iam-user/7.png)

    </details>

8. **Add tags - optional** card
   1. **Add tag**
      * Key `env`
      * Value `temp`
   2. Click **Create Policy** button

   <details>
    <summary><b>Add tags - optional</b> card</summary>

    ![Add tags - optional](images/create-iam-user/8.png)

    </details>

9. **Create user group** popup
   1. lookup for the recent policy
   2. Select it
   3. Click **Create user group** button

   <details>
    <summary><b>Create user group</b> popup</summary>

    ![Create user group](images/create-iam-user/9.png)

    </details>

10. **User groups** card
    1. Select the recent created group
    2. Click **Next** button

    <details>
    <summary><b>Create user group</b> popup</summary>

    ![User group](images/create-iam-user/10.png)

    </details>

11. **Add tags - optional** card
    1.  **Add tag**
        * Key `env`
        * Value `temp`
    2. Click **Create user** button

    <details>
    <summary><b>Add tags - optional</b> popup</summary>

    ![Add tags - optional](images/create-iam-user/11.png)

    </details>

## Create access key for IAM User

1. **IAM > User**
   1. Click on the `github_actions` user

   <details>
        <summary>
                <b>IAM users</b>
        </summary>

    ![IAM Users](images/create-access-key/1.png)
   </details>

2. **Security Credentials tab**
   1. Click on the **Security credentials** tab
   2. Scroll down to the **Access Keys** card

   <details>
        <summary>
                <b>Security Credentials</b>
        </summary>

    ![IAM User](images/create-access-key/2.png)
   </details>

3. **Access keys**
   1. Click on the **Create access key** button

   <details>
        <summary>
                <b>Access keys</b> card
        </summary>

    ![Access keys](images/create-access-key/3.png)
   </details>

4. **Access key best practices & alternative**
   1. Select **Command Line Interface (CLI)**
   2. Check `I understand the above recommendation and want to proceed to create an access key` at the bottom
   3. Scroll down and click on the **Next** button

   <details>
        <summary>
                <b>Access key best practices & alternative</b>
        </summary>

    ![Access key best practices & alternative](images/create-access-key/4.png)
   </details>

5. **Set description tag - optional**
   1. Fill the **Description tag value** with `GitHub workflow to upload a static website`
   2. Click on **Create access key** button

   <details>
        <summary>
                <b>Set description tag - optional</b> card
        </summary>

    ![Set description tag - optional](images/create-access-key/5.png)
   </details>

6. **Retrieve access keys**
   1. Save the **Access key** and **Secret access key** values
   2. Click on the **Done** button

   <details>
        <summary>
                <b>Retrieve access keys</b> section
        </summary>

    ![Retrieve access keys](images/create-access-key/6.png)
   </details>

## Setting the secrets up in the GitHub repository

1. **GitHub Secrets**
   1. Go to the **Settings** tab of the repository
   2. In the left panel go to **Security > Secrets and variables > Actions**
   3. Click on the **New repository secret**

   <details>
        <summary>
                <b>GitHub Secrets</b> section
        </summary>

    ![GitHub Secrets](images/setup-github-secrets/1.png)
   </details>

2. **Add Repository secret**
   1.  Fill the **Name** field with `AWS_ACCESS_KEY_ID`
   2.  Fill the **Secret** field with *The github_action access key*
   3.  Click on **Add secret** button
   4.  Repeat with the following secrets
       - `AWS_SECRET_ACCESS_KEY`
         - *The secret of the github_action access key*
       - `AWS_S3_BUCKET`
         - `web.richard-adolfo-vega-almanza`

    <details>
        <summary>
                <b>Add Repository secret</b> section
        </summary>

    ![Add Repository secret](images/setup-github-secrets/2.png)
   </details>

## GitHub repository changes

My personal website already have a GitHub workflow, so I edited it a little

So, I

1. Created a new branch name `epam-aws`
2. Removed the triggers based on commits
3. Changed or removed values made for GitHub pages
4. Replaced the deployment action made for GitHub pages to AWS S3
5. Removed the folder `fontawesome-5` from the rendered website to avoid tons of PUT calling to upload all those tiny files, avoiding reaching the free tier limit of S3 by just one workflow
6. Triggered manual;y the workflow

<details>
    <summary>
            <b>Commit changes</b> Diff
    </summary>

![Commit changes 1](images/github-changes/1.png)
![Commit changes 2](images/github-changes/2.png)
</details>

## Static website hosting - S3

1. **AWS Console > S3 > Buckets > aws.richard-adolfo-vega-almanza**
   1. Click on **Properties** tab
   2. Scroll down to the **Static website hosting** card at the end of the page

   <details>
        <summary>
                <b>Bucket's properties</b> tab
        </summary>

    ![Bucket's properties tab](images/s3-static-website/1.png)
   </details>

2. **Static website hosting**
   1. Click on the **Edit** button

   <details>
        <summary>
                <b>Static website hosting</b> card
        </summary>

    ![Static website hosting card](images/s3-static-website/2.png)
   </details>

3. **Static website hosting**
   1. Select **Static website hosting > Enabled**
   2. Select **Hosting type > Host a static website**
   3. Fill the **Index document** field, in my case `index.html`
   4. Fill the **Error document - optional** field, in my case `404.html`
   5. Scroll down and click on the **Save changes** button

   <details>
        <summary>
                <b>Static website hosting</b> card
        </summary>

    ![Static website hosting card](images/s3-static-website/3.png)
   </details>

4. **Get the Website URL**
   1. Click on the [*Link*](http://web.richard-adolfo-vega-almanza.s3-website-us-east-1.amazonaws.com/) at the bottom of the **Static website hosting** card

   <details>
        <summary>
                <b>Static website hosting</b> card
        </summary>

    ![Static website hosting card](images/s3-static-website/4.png)
   </details>

   <details>
        <summary>
                <b>Main/Home page</b>
        </summary>

    ![Home page](images/s3-static-website/5.png)
   </details>

   <details>
        <summary>
                <b>Error/NotFound Page</b>
        </summary>

    ![Error 404 page](images/s3-static-website/6.png)
   </details>
