const { exec } = require('child_process');

const repoName = 'my-new-nodejs-project';
const description = 'A new project created with a Node.js script.';
const visibility = '--public'; // or '--private'

const command = `gh repo create ${repoName} --description "${description}" ${visibility}`;

exec(command, (error, stdout, stderr) => {
  if (error) {
    console.error(`exec error: ${error}`);
    return;
  }
  console.log(`stdout: ${stdout}`);
  console.error(`stderr: ${stderr}`);
  console.log(`Repository "${repoName}" created successfully!`);
});
