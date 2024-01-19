# Automated Laravel.io Application Deployment and Optimization

This repository contains the code and documentation for an assignment aimed at automating the deployment and optimizing the performance of the Laravel.io application using Ansible and Google Kubernetes Engine (GKE). The assignment is divided into two tasks, each with specific objectives and requirements.

## Task 1 - Automatic Installation and Configuration

### Objective

The primary goal of Task 1 is to automate the installation and configuration of the Laravel.io application on GKE. The key objectives include:

- Utilizing Ansible for automated deployment.
- Segregating Laravel.io application components into separate pods.
- Minimizing manual steps in installation and configuration.
- Ensuring the application can be stopped and restarted without data loss.
- Adhering to the provided Ansible playbooks' structure and functionalities.

## Task 2 - Application Exploration and Optimization

### Objective

Task 2 involves assessing and optimizing the performance, scalability, and resilience of the Laravel.io application. Key objectives are:

- Identifying potential performance bottlenecks as the number of clients grows.
- Evaluating the application's performance under varying loads and workloads.
- Pinpointing single points of failure within application components.

### Project Report

The final project report, detailing findings, optimizations, and their impact, can be found in the [report](/report) directory. Please refer to this report for a comprehensive overview of the assignment.

### How to deploy the project:

Get your gcp service account json token file.
Update its path in the gcp.yml file and all the other project specific placeholders

You must deploy your cluster before usage, for that run the following command
```ansible-playbook -i ./inventory/gcp.yml ./gke-cluster-create.yml```

After the clusters creation you can deploy the app using 
```ansible-playbook -i ./inventory/gcp.yml ./laravelio-deploy.yml  <flags>```

The flags can be:
  - `-e p=password` (if you use this option the encryption password will be the same as the decryption password)
  - `-e old_password=password1 -e new_password=password2` (if you use this option you will change the encryption password with the value in new_password)
  - `-e benchmark_solution=true` (this will run the default jmeter tests, get the mainpage and login)(*optional*)
  - `-e create_dashboard=true`(this will create a default dashboard in the GCP monitoring tab)(*optional*)
  - `-e dashboard_path=path`(this flag combined with the previous will create the dashboard in the path instead of using the default one)(*optional*)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The Laravel.io application: [Laravel.io GitHub Repository](https://github.com/laravelio/laravel.io)
- Google Kubernetes Engine: [GKE](https://cloud.google.com/kubernetes-engine)

For any questions or assistance, please feel free to reach out to [[Nelson Almeida] (pg52697@alunos.uminho.pt]()) , [Francisca Lemos][(pg52693@alunos.uminho.pt]()), [[Nuno Costa](pg52698@alunos.uminho.pt]()), [José Martins][(pg53968@alunos.uminho.pt]()).

Happy coding!
