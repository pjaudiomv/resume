<script lang="ts">
  import { Card, Button, Badge, Timeline, TimelineItem, DarkMode } from 'flowbite-svelte';
  import { onMount } from 'svelte';

  let mounted = $state(false);
  let skillsVisible = $state(false);
  let activeSkillGroup = $state(-1);

  onMount(() => {
    mounted = true;
    setTimeout(() => {
      skillsVisible = true;
    }, 300);
  });

  // Data from user
  const summary = `Innovative and results-driven Principal DevSecOps Engineer with extensive experience designing and implementing secure, scalable, and compliant infrastructure solutions for the Department of Defense (DoD) and commercial sectors. Adept at leveraging cutting-edge tools and technologies, including Terraform, Kubernetes, Iron Bank, and Big Bang, to drive operational excellence and accelerate delivery pipelines. Proven expertise in Zero Trust Architecture, container hardening, and compliance with Risk Management Framework (RMF) and STIG standards. Skilled in leading cross-functional teams, streamlining processes, and deploying infrastructure across multi-cloud and air-gapped environments.

Possesses CompTIA Security+ certification and an active Secret clearance, enabling seamless collaboration in high-security environments. Recognized for delivering mission-critical solutions in DevSecOps, CI/CD, and Infrastructure as Code (IaC) while maintaining the highest standards of security and reliability. Dedicated to enhancing mission readiness and operational efficiency through innovative and compliant solutions tailored to evolving DoD and enterprise needs.`;

  const skills = [
    {
      group: 'DevSecOps & CI/CD',
      items: ['GitLab', 'Jenkins', 'Twistlock', 'Anchore', 'ArgoCD'],
      icon: '🚀',
      color: 'bg-gradient-to-r from-blue-500 to-purple-600'
    },
    {
      group: 'Infrastructure & Cloud',
      items: ['Terraform', 'Packer', 'Kubernetes', 'Helm', 'AWS', 'Azure'],
      icon: '☁️',
      color: 'bg-gradient-to-r from-green-500 to-teal-600'
    },
    {
      group: 'Programming & Scripting',
      items: ['Python', 'React', 'Bash', 'PHP'],
      icon: '💻',
      color: 'bg-gradient-to-r from-orange-500 to-red-600'
    },
    {
      group: 'Security & Compliance',
      items: ['Zero Trust Architecture', 'RMF', 'STIGs', 'NIST 800-53'],
      icon: '🔒',
      color: 'bg-gradient-to-r from-red-500 to-pink-600'
    },
    {
      group: 'Tools & Platforms',
      items: ['ELK Stack', 'Big Bang', 'Iron Bank', 'EKS', 'Okta', 'Istio'],
      icon: '🛠️',
      color: 'bg-gradient-to-r from-purple-500 to-indigo-600'
    }
  ];

  const experience = [
    {
      title: 'Principal Platform Engineer',
      company: 'Radius Method',
      location: 'Summerville, SC',
      period: 'May 2023 - present',
      color: 'from-blue-600 to-purple-600',
      projects: [
        {
          name: 'Cloud Native Access Point (CNAP)',
          bullets: [
            'Deployed GitLab Runner EKS clusters to both CNAP staging and production environments to support a unified Terraform pipeline.',
            'Converted all staging and production Terragrunt configurations to Terraform, simplifying and unifying infrastructure management.',
            'Created a unified Terraform pipeline enabling seamless deployment to staging and production environments from a single codebase, ensuring environmental parity.',
            'Deployed a fully unified Terraform repository for production and staged Terraform setups to streamline deployments.',
            'Provisioned infrastructure management EKS clusters for staging and production using custom EKS Terraform modules.',
            'Built robust Packer pipelines for continuous integration of golden AMIs, including STIG-compliant EKS AMIs for use in EKS clusters.',
            'Developed a Terraform module for border mod gateway load balancer endpoints, enhancing network infrastructure reliability.'
          ]
        },
        {
          name: 'Iron Bank Pipelines & Operations (POPs)',
          bullets: [
            "Operations and sustainment for Iron Bank, the Department of Defense's (DoD) hardened container repository under Platform One, ensuring compliance with the Defense Services Organization Investigator (DSOI) initiative.",
            'Maintained and enhanced CI/CD pipeline infrastructure to automate container building, security assessments, and accreditation processes.',
            'Implemented and optimized Infrastructure as Code (IaC) and Configuration as Code (CaC) solutions for multi-cloud and air-gapped environments, leveraging Terraform, Ansible, Helm, and Kubernetes Operators.',
            'Drove security improvements across Platform One stacks by integrating cybersecurity tools such as Twistlock, Anchore, and EFK logging.',
            'Maintained the Authority to Operate (ATO) for Iron Bank components, aligning with DoD Risk Management Framework (RMF) standards.',
            'Authored and automated comprehensive onboarding and accreditation documentation, streamlining the deployment of DevSecOps pipelines in secure environments.',
            'Collaborated with cross-functional teams to continuously enhance container hardening standards and Platform One DevSecOps processes.'
          ]
        }
      ]
    },
    {
      title: 'IT Software Engineer',
      company: 'Rebellion Defense',
      location: 'Summerville, SC',
      period: 'July 2021 – April 2023',
      color: 'from-green-600 to-teal-600',
      bullets: [
        'Managed and maintained GitLab CI/CD pipelines for secure and efficient software delivery.',
        'Deployed self-hosted software solutions in AWS using ECS and EKS, ensuring scalability and compliance.',
        'Designed Kubernetes authentication integrations with Okta and implemented Terraform-based infrastructure upgrades.',
        'Automated IT workflows, improving team productivity and operational reliability.',
        'Developed and maintained compliance pipelines for enhanced application and infrastructure security.'
      ]
    },
    {
      title: 'Principal SRE & Security Engineer',
      company: 'F9 Teams (Kessel Run – Air Force, SecOps / Cloud Teams)',
      location: 'Summerville, SC',
      period: 'May 2019 – July 2021',
      color: 'from-purple-600 to-pink-600',
      bullets: [
        "Built and maintained Kessel Run's software factory, serving as the backbone for rapid application development across dozens of Air Force teams.",
        'Automated compliance pipelines to ensure security governance and Zero Trust implementations.',
        'Developed egress proxy solutions using ECS and transitioned core applications from Pivotal Cloud Foundry to Kubernetes.',
        'Integrated AWS, Okta, and Vault to deliver dynamic credential management in both local and CI environments.'
      ]
    },
    {
      title: 'Freelance Engineer',
      company: 'Self-Employed',
      location: 'Summerville, SC',
      period: 'Spring 2009 – 2019',
      color: 'from-orange-600 to-red-600',
      bullets: [
        'Delivered web and mobile applications, integrating CMS and e-commerce platforms for diverse industries.',
        'Provided cloud consulting services and cross-platform app development for iOS and Android.'
      ]
    },
    {
      title: 'Programmer, Home & Commercial Automation',
      company: "Martha's Vineyard Sound and Security",
      location: 'Oak Bluffs, MA',
      period: 'Summer 2013 – Fall 2018',
      color: 'from-indigo-600 to-blue-600',
      bullets: ['Programmed advanced home and commercial automation systems, working with Crestron, Sonos, and other high-end platforms.']
    },
    {
      title: 'Freelance Audio Engineer',
      company: 'Self-Employed',
      location: 'Edgartown, MA',
      period: 'Fall 2005 – 2019',
      color: 'from-teal-600 to-green-600',
      bullets: ['Delivered audio and lighting solutions for high-profile events, including performances by Lauryn Hill, Stephen Marley, and corporate and political functions.']
    }
  ];

  const education = [
    {
      degree: 'CompTIA Security+ (Active Secret Clearance)',
      school: 'Professional Certification',
      period: 'Current'
    },
    {
      degree: 'Associates in Audio and Media Technology',
      school: 'New England Institute of Art',
      period: '2007'
    }
  ];

  const clearance = {
    level: 'Secret Clearance',
    status: 'Active',
    issuer: 'U.S. Department of Defense'
  };
</script>

<div class="min-h-screen bg-gradient-to-br from-slate-50 via-blue-50 to-indigo-100 transition-all duration-500 dark:from-gray-900 dark:via-slate-900 dark:to-indigo-950">
  <!-- Animated background elements -->
  <div class="pointer-events-none fixed inset-0 overflow-hidden">
    <div class="animate-pulse-slow absolute -top-40 -right-40 h-80 w-80 rounded-full bg-gradient-to-br from-blue-400/20 to-purple-600/20 blur-3xl"></div>
    <div class="animate-pulse-slow absolute -bottom-40 -left-40 h-80 w-80 rounded-full bg-gradient-to-br from-teal-400/20 to-blue-600/20 blur-3xl" style="animation-delay: -1s;"></div>
  </div>

  <div class="relative mx-auto max-w-4xl px-4 py-12">
    <!-- Header -->
    <Card class="glass-effect mb-8 border-0 bg-white/80 shadow-2xl dark:bg-gray-800/80 {mounted ? 'animate-slide-in-up' : 'opacity-0'}">
      <div class="flex flex-col gap-6 lg:flex-row lg:items-center lg:justify-between">
        <div class="space-y-2">
          <h1 class="gradient-text text-4xl font-bold lg:text-5xl">Patrick Joyce</h1>
          <h2 class="bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-xl font-semibold text-transparent lg:text-2xl">Principal DevSecOps Engineer</h2>
          <div class="flex items-center gap-2 text-gray-600 dark:text-gray-300">
            <div class="h-2 w-2 animate-pulse rounded-full bg-green-500"></div>
            <span class="text-sm font-medium">Available for opportunities</span>
          </div>
          <a href="mailto:therealpatrickjoyce@gmail.com" class="inline-flex items-center gap-2 text-sm text-gray-600 transition-colors hover:text-blue-600 dark:text-gray-300 dark:hover:text-blue-400">
            <span class="floating-icon">📧</span>
            therealpatrickjoyce@gmail.com
          </a>
        </div>
        <div class="flex items-center gap-3">
          <DarkMode size="lg" ariaLabel="Toggle dark mode" class="rounded-xl bg-gradient-to-r from-slate-200 to-slate-300 p-3 transition-all hover:shadow-lg dark:from-gray-700 dark:to-gray-600" />
          <Button
            color="primary"
            class="transform rounded-xl border-0 bg-gradient-to-r from-blue-600 to-purple-600 px-6 py-3 shadow-lg transition-all hover:scale-105 hover:from-blue-700 hover:to-purple-700 hover:shadow-xl"
            href="mailto:therealpatrickjoyce@gmail.com"
          >
            <span class="mr-2">💬</span>
            Let's Connect
          </Button>
        </div>
      </div>
    </Card>

    <!-- Summary -->
    <Card class="glass-effect mb-8 border-0 bg-white/90 shadow-xl dark:bg-gray-800/90 {mounted ? 'animate-slide-in-left' : 'opacity-0'}" style="animation-delay: 0.2s;">
      <div class="flex items-start gap-4">
        <div class="floating-icon text-3xl">🎯</div>
        <div>
          <h3 class="mb-4 flex items-center gap-2 text-xl font-bold text-gray-800 dark:text-gray-100">
            Professional Summary
            <div class="h-1 w-12 rounded-full bg-gradient-to-r from-blue-500 to-purple-500"></div>
          </h3>
          <p class="leading-relaxed text-gray-700 dark:text-gray-300">{summary}</p>
        </div>
      </div>
    </Card>

    <!-- Skills -->
    <Card class="glass-effect mb-8 border-0 bg-white/90 shadow-xl dark:bg-gray-800/90 {skillsVisible ? 'animate-fade-in-scale' : 'opacity-0'}" style="animation-delay: 0.4s;">
      <div class="mb-6 flex items-start gap-4">
        <div class="floating-icon text-3xl">⚡</div>
        <div>
          <h3 class="flex items-center gap-2 text-xl font-bold text-gray-800 dark:text-gray-100">
            Technical Expertise
            <div class="h-1 w-12 rounded-full bg-gradient-to-r from-green-500 to-teal-500"></div>
          </h3>
        </div>
      </div>

      <div class="grid gap-6">
        {#each skills as skillGroup, index}
          <div class="group" role="listitem" onmouseenter={() => (activeSkillGroup = index)} onmouseleave={() => (activeSkillGroup = -1)}>
            <div class="mb-3 flex items-center gap-3">
              <div class="transform text-2xl transition-transform group-hover:scale-110">
                {skillGroup.icon}
              </div>
              <span class="text-lg font-bold text-gray-800 dark:text-gray-100">
                {skillGroup.group}
              </span>
              <div class="h-1 flex-1 bg-gradient-to-r {skillGroup.color} rounded-full opacity-30 transition-opacity group-hover:opacity-60"></div>
            </div>
            <div class="flex flex-wrap gap-3">
              {#each skillGroup.items as skill, skillIndex}
                <Badge
                  color="blue"
                  class="skill-badge border border-gray-200 bg-white/80 px-4 py-2 text-sm font-medium text-gray-800 hover:border-blue-400 hover:bg-blue-50 dark:border-gray-600 dark:bg-gray-700/80 dark:text-gray-200 dark:hover:border-blue-500 dark:hover:bg-blue-900/20"
                  style="animation-delay: {skillIndex * 0.1}s;"
                >
                  {skill}
                </Badge>
              {/each}
            </div>
          </div>
        {/each}
      </div>
    </Card>

    <!-- Experience -->
    <Card class="glass-effect mb-8 border-0 bg-white/90 shadow-xl dark:bg-gray-800/90 {mounted ? 'animate-slide-in-up' : 'opacity-0'}" style="animation-delay: 0.6s;">
      <div class="mb-6 flex items-start gap-4">
        <div class="floating-icon text-3xl">🚀</div>
        <div>
          <h3 class="flex items-center gap-2 text-xl font-bold text-gray-800 dark:text-gray-100">
            Professional Experience
            <div class="h-1 w-12 rounded-full bg-gradient-to-r from-purple-500 to-pink-500"></div>
          </h3>
        </div>
      </div>

      <Timeline>
        {#each experience as job, jobIndex}
          <TimelineItem title={`${job.title} @ ${job.company}`} date={job.period} class="experience-card">
            <div class="space-y-3">
              <div class="flex items-center gap-2 text-sm text-gray-500 dark:text-gray-400">
                <span>📍</span>
                {job.location}
              </div>

              {#if job.projects}
                {#each job.projects as project, projectIndex}
                  <div class="border-gradient-to-b border-l-4 {job.color} rounded-r-lg bg-gray-50/50 py-2 pl-4 dark:bg-gray-700/30">
                    <div class="mb-2 flex items-center gap-2 text-lg font-bold text-gray-800 dark:text-gray-200">
                      <span class="text-xl">🎯</span>
                      {project.name}
                    </div>
                    <ul class="space-y-2 text-gray-700 dark:text-gray-300">
                      {#each project.bullets as bullet, bulletIndex}
                        <li class="flex items-start gap-2 leading-relaxed" style="animation-delay: {bulletIndex * 0.1}s;">
                          <span class="mt-1.5 text-xs text-blue-500 dark:text-blue-400">●</span>
                          <span>{bullet}</span>
                        </li>
                      {/each}
                    </ul>
                  </div>
                {/each}
              {:else}
                <ul class="space-y-2 text-gray-700 dark:text-gray-300">
                  {#each job.bullets as bullet, bulletIndex}
                    <li class="flex items-start gap-2 leading-relaxed" style="animation-delay: {bulletIndex * 0.1}s;">
                      <span class="mt-1.5 text-xs text-blue-500 dark:text-blue-400">●</span>
                      <span>{bullet}</span>
                    </li>
                  {/each}
                </ul>
              {/if}
            </div>
          </TimelineItem>
        {/each}
      </Timeline>
    </Card>

    <!-- Security Clearance -->
    <Card class="glass-effect mb-8 border-0 bg-white/90 shadow-xl dark:bg-gray-800/90 {mounted ? 'animate-slide-in-up' : 'opacity-0'}" style="animation-delay: 0.7s;">
      <div class="p-6">
        <div class="mb-6 flex items-start gap-4">
          <div class="floating-icon text-3xl">🛡️</div>
          <div>
            <h3 class="flex items-center gap-2 text-xl font-bold text-gray-800 dark:text-gray-100">
              Security Clearance
              <div class="h-1 w-12 rounded-full bg-gradient-to-r from-blue-500 to-indigo-500"></div>
            </h3>
          </div>
        </div>

        <div class="flex items-center gap-4 rounded-xl border-2 border-blue-200 bg-gradient-to-r from-blue-50 to-indigo-50 p-6 dark:border-blue-700 dark:from-blue-900/20 dark:to-indigo-900/20">
          <div class="text-3xl">🔐</div>
          <div class="flex-1">
            <div class="text-xl font-bold text-blue-800 dark:text-blue-200">{clearance.level}</div>
            <div class="font-medium text-blue-600 dark:text-blue-300">{clearance.status} • {clearance.issuer}</div>
          </div>
          <div class="rounded-full border border-green-300 bg-green-100 px-4 py-2 text-sm font-bold text-green-800 dark:border-green-600 dark:bg-green-900/30 dark:text-green-200">ACTIVE</div>
        </div>
      </div>
    </Card>

    <!-- Education & Certifications -->
    <Card class="glass-effect border-0 bg-white/90 shadow-xl dark:bg-gray-800/90 {mounted ? 'animate-fade-in-scale' : 'opacity-0'}" style="animation-delay: 0.8s;">
      <div class="mb-6 flex items-start gap-4">
        <div class="floating-icon text-3xl">🎓</div>
        <div>
          <h3 class="flex items-center gap-2 text-xl font-bold text-gray-800 dark:text-gray-100">
            Education & Certifications
            <div class="h-1 w-12 rounded-full bg-gradient-to-r from-orange-500 to-red-500"></div>
          </h3>
        </div>
      </div>

      <div class="space-y-4">
        {#each education as edu, index}
          <div
            class="flex items-center gap-4 rounded-xl border border-gray-200 bg-gradient-to-r from-gray-50 to-blue-50 p-4 transition-all hover:shadow-lg dark:border-gray-600 dark:from-gray-700 dark:to-blue-900/20"
            style="animation-delay: {index * 0.2}s;"
          >
            <div class="text-2xl">
              {edu.degree.includes('Security+') ? '🛡️' : '📚'}
            </div>
            <div class="flex-1">
              <div class="font-bold text-gray-800 dark:text-gray-100">{edu.degree}</div>
              <div class="text-gray-600 dark:text-gray-300">{edu.school}</div>
            </div>
            <div class="rounded-full bg-blue-100 px-3 py-1 text-sm font-medium text-blue-800 dark:bg-blue-900/30 dark:text-blue-200">
              {edu.period}
            </div>
          </div>
        {/each}
      </div>
    </Card>
  </div>
</div>

<style>
  @keyframes slideInUp {
    from {
      opacity: 0;
      transform: translateY(30px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes slideInLeft {
    from {
      opacity: 0;
      transform: translateX(-30px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }

  @keyframes fadeInScale {
    from {
      opacity: 0;
      transform: scale(0.8);
    }
    to {
      opacity: 1;
      transform: scale(1);
    }
  }

  @keyframes pulse {
    0%,
    100% {
      opacity: 1;
    }
    50% {
      opacity: 0.7;
    }
  }

  .animate-slide-in-up {
    animation: slideInUp 0.6s ease-out;
  }

  .animate-slide-in-left {
    animation: slideInLeft 0.6s ease-out;
  }

  .animate-fade-in-scale {
    animation: fadeInScale 0.5s ease-out;
  }

  .animate-pulse-slow {
    animation: pulse 2s ease-in-out infinite;
  }

  .glass-effect {
    backdrop-filter: blur(10px);
    background: rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.2);
  }

  .skill-badge {
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    transform: translateY(0);
  }

  .skill-badge:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
  }

  .experience-card {
    transition: all 0.3s ease;
    border-left: 4px solid transparent;
  }

  .experience-card:hover {
    transform: translateX(4px);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
  }

  .gradient-text {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .floating-icon {
    animation: float 3s ease-in-out infinite;
  }

  @keyframes float {
    0%,
    100% {
      transform: translateY(0px);
    }
    50% {
      transform: translateY(-10px);
    }
  }
</style>
