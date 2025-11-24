// pages/_app.js
import '../styles/globals.css';

function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />;
}

export default MyApp;

// pages/_document.js
import { Html, Head, Main, NextScript } from 'next/document';

export default function Document() {
  return (
    <Html lang="en">
      <Head>
        <link rel="preconnect" href="https://fonts.googleapis.com" />
        <link rel="preconnect" href="https://fonts.gstatic.com" crossOrigin="anonymous" />
        <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet" />
      </Head>
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  );
}

// styles/globals.css
import '@fontsource/inter/300.css';
import '@fontsource/inter/400.css';
import '@fontsource/inter/500.css';
import '@fontsource/inter/600.css';
import '@fontsource/inter/700.css';

@tailwind base;
@tailwind components;
@tailwind utilities;

// pages/index.js
import Head from 'next/head';
import Link from 'next/link';
import { useState } from 'react';
import { 
  ArrowRight, 
  Shield, 
  Zap, 
  Globe, 
  Code, 
  Smartphone, 
  Monitor, 
  Users, 
  Award, 
  Star, 
  Mail, 
  Phone, 
  MapPin,
  Menu,
  X,
  CheckCircle,
  ChevronRight
} from 'lucide-react';

export default function Home() {
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);

  const services = [
    {
      title: "Web App Design",
      description: "Custom web applications tailored to your business needs with modern UI/UX design.",
      icon: <Code className="w-8 h-8" />,
      features: ["Responsive Design", "Modern UI/UX", "User-Centric Approach"]
    },
    {
      title: "Website Maintenance",
      description: "Comprehensive maintenance plans to keep your website secure and up-to-date.",
      icon: <Shield className="w-8 h-8" />,
      features: ["Security Updates", "Performance Optimization", "Content Management"]
    },
    {
      title: "Lead Sourcing",
      description: "Strategic marketing solutions to generate qualified leads for your business.",
      icon: <Users className="w-8 h-8" />,
      features: ["SEO Optimization", "Social Media Marketing", "Email Campaigns"]
    }
  ];

  const portfolio = [
    {
      title: "E-commerce Platform",
      category: "Web App",
      description: "Custom e-commerce solution with inventory management and payment integration.",
      image: "https://placehold.co/600x400/3b82f6/white?text=E-commerce+Platform",
      beforeAfter: {
        before: "https://placehold.co/300x200/ef4444/white?text=Before",
        after: "https://placehold.co/300x200/22c55e/white?text=After"
      }
    },
    {
      title: "SaaS Dashboard",
      category: "Web App",
      description: "Analytics dashboard with real-time data visualization.",
      image: "https://placehold.co/600x400/8b5cf6/white?text=SaaS+Dashboard",
      beforeAfter: {
        before: "https://placehold.co/300x200/ef4444/white?text=Before",
        after: "https://placehold.co/300x200/22c55e/white?text=After"
      }
    },
    {
      title: "Corporate Website",
      category: "Website",
      description: "Modern corporate website with CMS integration.",
      image: "https://placehold.co/600x400/10b981/white?text=Corporate+Site",
      beforeAfter: {
        before: "https://placehold.co/300x200/ef4444/white?text=Before",
        after: "https://placehold.co/300x200/22c55e/white?text=After"
      }
    }
  ];

  const testimonials = [
    {
      name: "Sarah Johnson",
      role: "CEO, TechStart Inc.",
      content: "The team delivered beyond our expectations. Our new web app increased user engagement by 150%.",
      rating: 5
    },
    {
      name: "Michael Chen",
      role: "Marketing Director, GrowthCo",
      content: "Professional service with attention to detail. The before/after results speak for themselves.",
      rating: 5
    },
    {
      name: "Emily Rodriguez",
      role: "Founder, StartupHub",
      content: "Responsive team that understood our vision. The final product exceeded all expectations.",
      rating: 5
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>WebDev Pro - Professional Web Development Services</title>
        <meta name="description" content="Professional web development services including custom web apps, website maintenance, and digital marketing solutions." />
      </Head>

      {/* Header */}
      <header className="bg-white shadow-sm sticky top-0 z-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            <Link href="/" className="text-2xl font-bold text-blue-600">
              WebDev Pro
            </Link>
            
            <nav className="hidden md:flex space-x-8">
              <Link href="/" className="text-gray-700 hover:text-blue-600 font-medium">Home</Link>
              <Link href="/services" className="text-gray-700 hover:text-blue-600 font-medium">Services</Link>
              <Link href="/web-app-design" className="text-gray-700 hover:text-blue-600 font-medium">Web App Design</Link>
              <Link href="/maintenance" className="text-gray-700 hover:text-blue-600 font-medium">Maintenance</Link>
              <Link href="/marketing" className="text-gray-700 hover:text-blue-600 font-medium">Marketing</Link>
              <Link href="/portfolio" className="text-gray-700 hover:text-blue-600 font-medium">Portfolio</Link>
              <Link href="/about" className="text-gray-700 hover:text-blue-600 font-medium">About</Link>
              <Link href="/contact" className="text-gray-700 hover:text-blue-600 font-medium">Contact</Link>
            </nav>
            
            <button 
              className="md:hidden p-2"
              onClick={() => setMobileMenuOpen(!mobileMenuOpen)}
            >
              {mobileMenuOpen ? <X size={24} /> : <Menu size={24} />}
            </button>
          </div>
        </div>
        
        {mobileMenuOpen && (
          <div className="md:hidden bg-white border-t">
            <div className="px-2 pt-2 pb-3 space-y-1">
              <Link href="/" className="block px-3 py-2 text-gray-700 hover:text-blue-600">Home</Link>
              <Link href="/services" className="block px-3 py-2 text-gray-700 hover:text-blue-600">Services</Link>
              <Link href="/web-app-design" className="block px-3 py-2 text-gray-700 hover:text-blue-600">Web App Design</Link>
              <Link href="/maintenance" className="block px-3 py-2 text-gray-700 hover:text-blue-600">Maintenance</Link>
              <Link href="/marketing" className="block px-3 py-2 text-gray-700 hover:text-blue-600">Marketing</Link>
              <Link href="/portfolio" className="block px-3 py-2 text-gray-700 hover:text-blue-600">Portfolio</Link>
              <Link href="/about" className="block px-3 py-2 text-gray-700 hover:text-blue-600">About</Link>
              <Link href="/contact" className="block px-3 py-2 text-gray-700 hover:text-blue-600">Contact</Link>
            </div>
          </div>
        )}
      </header>

      {/* Hero Section */}
      <section className="bg-gradient-to-r from-blue-600 to-purple-700 text-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24">
          <div className="text-center">
            <h1 className="text-4xl md:text-6xl font-bold mb-6">
              Transform Your Digital Presence
            </h1>
            <p className="text-xl md:text-2xl mb-8 max-w-3xl mx-auto">
              Professional web development services to help your business grow online. Custom web apps, websites, and marketing solutions.
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center">
              <Link href="/contact" className="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg text-lg hover:bg-gray-100 transition-colors flex items-center justify-center gap-2">
                Get Started <ArrowRight size={20} />
              </Link>
              <Link href="/portfolio" className="bg-transparent border-2 border-white text-white font-bold py-3 px-8 rounded-lg text-lg hover:bg-white hover:text-blue-600 transition-colors">
                View Portfolio
              </Link>
            </div>
          </div>
        </div>
      </section>

      {/* Benefits Section */}
      <section className="py-16 bg-gray-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-12">
            <h2 className="text-3xl font-bold text-gray-900 mb-4">Why Choose WebDev Pro?</h2>
            <p className="text-lg text-gray-600 max-w-2xl mx-auto">
              We combine technical expertise with strategic thinking to deliver solutions that drive results.
            </p>
          </div>
          
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div className="bg-white p-8 rounded-xl shadow-lg">
              <div className="text-blue-600 mb-4">
                <Zap className="w-12 h-12" />
              </div>
              <h3 className="text-xl font-bold mb-2">Fast Delivery</h3>
              <p className="text-gray-600">Agile development process ensures quick turnaround times without compromising quality.</p>
            </div>
            
            <div className="bg-white p-8 rounded-xl shadow-lg">
              <div className="text-blue-600 mb-4">
                <Globe className="w-12 h-12" />
              </div>
              <h3 className="text-xl font-bold mb-2">Responsive Design</h3>
              <p className="text-gray-600">All solutions are optimized for desktop, tablet, and mobile devices.</p>
            </div>
            
            <div className="bg-white p-8 rounded-xl shadow-lg">
              <div className="text-blue-600 mb-4">
                <Award className="w-12 h-12" />
              </div>
              <h3 className="text-xl font-bold mb-2">Quality Assurance</h3>
              <p className="text-gray-600">Rigorous testing ensures your solution is reliable and bug-free.</p>
            </div>
          </div>
        </div>
      </section>

      {/* Services Section */}
      <section className="py-16">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-12">
            <h2 className="text-3xl font-bold text-gray-900 mb-4">Our Services</h2>
            <p className="text-lg text-gray-600 max-w-2xl mx-auto">
              Comprehensive digital solutions tailored to your business needs.
            </p>
          </div>
          
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {services.map((service, index) => (
              <div key={index} className="bg-white p-8 rounded-xl shadow-lg border border-gray-100 hover:shadow-xl transition-shadow">
                <div className="text-blue-600 mb-4">
                  {service.icon}
                </div>
                <h3 className="text-xl font-bold mb-2">{service.title}</h3>
                <p className="text-gray-600 mb-4">{service.description}</p>
                <ul className="space-y-2">
                  {service.features.map((feature, idx) => (
                    <li key={idx} className="flex items-center text-gray-600">
                      <CheckCircle className="w-4 h-4 text-green-500 mr-2" />
                      {feature}
                    </li>
                  ))}
                </ul>
                <Link href={`/${service.title.toLowerCase().replace(' ', '-')}`} className="mt-6 inline-flex items-center text-blue-600 font-medium hover:text-blue-800">
                  Learn More <ChevronRight size={16} className="ml-1" />
                </Link>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Portfolio Section */}
      <section className="py-16 bg-gray-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-12">
            <h2 className="text-3xl font-bold text-gray-900 mb-4">Our Work</h2>
            <p className="text-lg text-gray-600 max-w-2xl mx-auto">
              See how we've helped businesses transform their digital presence.
            </p>
          </div>
          
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {portfolio.map((project, index) => (
              <div key={index} className="bg-white rounded-xl shadow-lg overflow-hidden">
                <img 
                  src={project.image} 
                  alt={project.title} 
                  className="w-full h-48 object-cover"
                />
                <div className="p-6">
                  <span className="text-sm text-blue-600 font-medium">{project.category}</span>
                  <h3 className="text-xl font-bold mt-2 mb-2">{project.title}</h3>
                  <p className="text-gray-600 mb-4">{project.description}</p>
                  
                  <div className="flex gap-2 mb-4">
                    <div className="flex flex-col items-center">
                      <span className="text-xs text-gray-500 mb-1">Before</span>
                      <img src={project.beforeAfter.before} alt="Before" className="w-12 h-8 object-cover rounded" />
                    </div>
                    <div className="flex flex-col items-center">
                      <span className="text-xs text-gray-500 mb-1">After</span>
                      <img src={project.beforeAfter.after} alt="After" className="w-12 h-8 object-cover rounded" />
                    </div>
                  </div>
                  
                  <Link href="/portfolio" className="text-blue-600 font-medium hover:text-blue-800 flex items-center">
                    View Case Study <ChevronRight size={16} className="ml-1" />
                  </Link>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Testimonials */}
      <section className="py-16">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-12">
            <h2 className="text-3xl font-bold text-gray-900 mb-4">Client Testimonials</h2>
            <p className="text-lg text-gray-600 max-w-2xl mx-auto">
              Don't just take our word for it - hear from our satisfied clients.
            </p>
          </div>
          
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {testimonials.map((testimonial, index) => (
              <div key={index} className="bg-white p-8 rounded-xl shadow-lg">
                <div className="flex mb-4">
                  {[...Array(testimonial.rating)].map((_, i) => (
                    <Star key={i} className="w-5 h-5 text-yellow-400 fill-current" />
                  ))}
                </div>
                <p className="text-gray-600 mb-4 italic">"{testimonial.content}"</p>
                <div>
                  <p className="font-bold text-gray-900">{testimonial.name}</p>
                  <p className="text-gray-600 text-sm">{testimonial.role}</p>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section className="py-16 bg-blue-600 text-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <h2 className="text-3xl font-bold mb-4">Ready to Transform Your Digital Presence?</h2>
          <p className="text-xl mb-8 max-w-2xl mx-auto">
            Let's discuss how we can help your business grow online.
          </p>
          <Link href="/contact" className="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg text-lg hover:bg-gray-100 transition-colors inline-flex items-center">
            Get Started Today <ArrowRight size={20} className="ml-2" />
          </Link>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 text-white py-12">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid grid-cols-1 md:grid-cols-4 gap-8">
            <div>
              <h3 className="text-xl font-bold mb-4">WebDev Pro</h3>
              <p className="text-gray-400">
                Professional web development services to help your business grow online.
              </p>
            </div>
            <div>
              <h4 className="font-semibold mb-4">Services</h4>
              <ul className="space-y-2 text-gray-400">
                <li><Link href="/web-app-design">Web App Design</Link></li>
                <li><Link href="/maintenance">Website Maintenance</Link></li>
                <li><Link href="/marketing">Lead Sourcing</Link></li>
              </ul>
            </div>
            <div>
              <h4 className="font-semibold mb-4">Company</h4>
              <ul className="space-y-2 text-gray-400">
                <li><Link href="/about">About Us</Link></li>
                <li><Link href="/portfolio">Portfolio</Link></li>
                <li><Link href="/blog">Blog</Link></li>
              </ul>
            </div>
            <div>
              <h4 className="font-semibold mb-4">Contact</h4>
              <ul className="space-y-2 text-gray-400">
                <li className="flex items-center">
                  <Mail className="w-4 h-4 mr-2" />
                  contact@webdevpro.com
                </li>
                <li className="flex items-center">
                  <Phone className="w-4 h-4 mr-2" />
                  (555) 123-4567
                </li>
                <li className="flex items-center">
                  <MapPin className="w-4 h-4 mr-2" />
                  San Francisco, CA
                </li>
              </ul>
            </div>
          </div>
          <div className="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
            <p>&copy; 2025 WebDev Pro. All rights reserved.</p>
          </div>
        </div>
      </footer>
    </div>
  );
}

// pages/services.js
import Head from 'next/head';
import Link from 'next/link';
import { Code, Shield, Users, Zap, Globe, Monitor, Smartphone, Award } from 'lucide-react';

export default function Services() {
  const services = [
    {
      title: "Web App Design",
      description: "Custom web applications tailored to your business needs with modern UI/UX design.",
      icon: <Code className="w-12 h-12 text-blue-600" />,
      features: [
        "Responsive Design",
        "Modern UI/UX",
        "User-Centric Approach",
        "Scalable Architecture"
      ]
    },
    {
      title: "Website Maintenance",
      description: "Comprehensive maintenance plans to keep your website secure and up-to-date.",
      icon: <Shield className="w-12 h-12 text-blue-600" />,
      features: [
        "Security Updates",
        "Performance Optimization",
        "Content Management",
        "24/7 Monitoring"
      ]
    },
    {
      title: "Lead Sourcing",
      description: "Strategic marketing solutions to generate qualified leads for your business.",
      icon: <Users className="w-12 h-12 text-blue-600" />,
      features: [
        "SEO Optimization",
        "Social Media Marketing",
        "Email Campaigns",
        "Lead Generation"
      ]
    },
    {
      title: "E-commerce Solutions",
      description: "Complete online store solutions with payment integration and inventory management.",
      icon: <Globe className="w-12 h-12 text-blue-600" />,
      features: [
        "Payment Integration",
        "Inventory Management",
        "Order Processing",
        "Customer Support"
      ]
    },
    {
      title: "Mobile App Development",
      description: "Native and cross-platform mobile applications for iOS and Android.",
      icon: <Smartphone className="w-12 h-12 text-blue-600" />,
      features: [
        "Native Development",
        "Cross-Platform",
        "App Store Optimization",
        "Push Notifications"
      ]
    },
    {
      title: "CMS Development",
      description: "Custom content management systems for easy content updates and management.",
      icon: <Monitor className="w-12 h-12 text-blue-600" />,
      features: [
        "User-Friendly Interface",
        "Content Management",
        "Media Management",
        "User Permissions"
      ]
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Services - WebDev Pro</title>
        <meta name="description" content="Professional web development services including custom web apps, website maintenance, and digital marketing solutions." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Our Services</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            Comprehensive digital solutions tailored to your business needs. From custom web applications to ongoing maintenance and marketing.
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          {services.map((service, index) => (
            <div key={index} className="bg-white p-8 rounded-xl shadow-lg border border-gray-100 hover:shadow-xl transition-shadow">
              <div className="mb-6">
                {service.icon}
              </div>
              <h3 className="text-2xl font-bold mb-4">{service.title}</h3>
              <p className="text-gray-600 mb-6">{service.description}</p>
              <ul className="space-y-3">
                {service.features.map((feature, idx) => (
                  <li key={idx} className="flex items-center text-gray-700">
                    <div className="w-2 h-2 bg-blue-600 rounded-full mr-3"></div>
                    {feature}
                  </li>
                ))}
              </ul>
              <Link href={`/${service.title.toLowerCase().replace(' ', '-')}`} className="mt-6 inline-block text-blue-600 font-medium hover:text-blue-800">
                Learn More →
              </Link>
            </div>
          ))}
        </div>

        <div className="mt-16 bg-gradient-to-r from-blue-600 to-purple-700 rounded-2xl p-12 text-white text-center">
          <h2 className="text-3xl font-bold mb-4">Ready to Get Started?</h2>
          <p className="text-xl mb-8 max-w-2xl mx-auto">
            Contact us today to discuss how our services can help grow your business.
          </p>
          <Link href="/contact" className="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg text-lg hover:bg-gray-100 transition-colors inline-block">
            Contact Us
          </Link>
        </div>
      </div>
    </div>
  );
}

// pages/web-app-design.js
import Head from 'next/head';
import Link from 'next/link';
import { Code, Zap, Globe, Monitor, Smartphone, Award } from 'lucide-react';

export default function WebAppDesign() {
  const features = [
    {
      icon: <Zap className="w-8 h-8 text-blue-600" />,
      title: "Fast Development",
      description: "Agile development process ensures quick turnaround times without compromising quality."
    },
    {
      icon: <Globe className="w-8 h-8 text-blue-600" />,
      title: "Responsive Design",
      description: "All solutions are optimized for desktop, tablet, and mobile devices."
    },
    {
      icon: <Award className="w-8 h-8 text-blue-600" />,
      title: "Quality Assurance",
      description: "Rigorous testing ensures your solution is reliable and bug-free."
    },
    {
      icon: <Monitor className="w-8 h-8 text-blue-600" />,
      title: "User-Centric",
      description: "Design focused on user experience and intuitive navigation."
    }
  ];

  const process = [
    "Discovery & Planning",
    "UI/UX Design",
    "Development",
    "Testing & QA",
    "Deployment",
    "Maintenance"
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Web App Design - WebDev Pro</title>
        <meta name="description" content="Professional custom web application development services with modern UI/UX design." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Custom Web App Design</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            Transform your business ideas into powerful, user-friendly web applications that drive results.
          </p>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center mb-16">
          <div>
            <h2 className="text-3xl font-bold text-gray-900 mb-6">Why Choose Our Web App Design?</h2>
            <p className="text-gray-600 mb-6">
              We combine technical expertise with strategic thinking to deliver custom web applications that solve your business challenges and provide exceptional user experiences.
            </p>
            <ul className="space-y-4">
              {features.map((feature, index) => (
                <li key={index} className="flex items-start">
                  <div className="mt-1 mr-3">
                    {feature.icon}
                  </div>
                  <div>
                    <h3 className="font-bold text-gray-900">{feature.title}</h3>
                    <p className="text-gray-600">{feature.description}</p>
                  </div>
                </li>
              ))}
            </ul>
          </div>
          <div className="bg-gray-100 rounded-xl p-8">
            <img 
              src="https://placehold.co/600x400/3b82f6/white?text=Web+App+Design" 
              alt="Web App Design" 
              className="w-full h-64 object-cover rounded-lg"
            />
          </div>
        </div>

        <div className="mb-16">
          <h2 className="text-3xl font-bold text-center text-gray-900 mb-12">Our Development Process</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            {process.map((step, index) => (
              <div key={index} className="bg-white p-6 rounded-xl shadow-lg border border-gray-100">
                <div className="w-10 h-10 bg-blue-100 rounded-full flex items-center justify-center text-blue-600 font-bold mb-4">
                  {index + 1}
                </div>
                <h3 className="text-xl font-bold text-gray-900">{step}</h3>
              </div>
            ))}
          </div>
        </div>

        <div className="bg-gradient-to-r from-blue-600 to-purple-700 rounded-2xl p-12 text-white text-center">
          <h2 className="text-3xl font-bold mb-4">Ready to Start Your Project?</h2>
          <p className="text-xl mb-8 max-w-2xl mx-auto">
            Contact us today to discuss your web app requirements and get a custom quote.
          </p>
          <Link href="/contact" className="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg text-lg hover:bg-gray-100 transition-colors inline-block">
            Get Started
          </Link>
        </div>
      </div>
    </div>
  );
}

// pages/maintenance.js
import Head from 'next/head';
import Link from 'next/link';
import { Shield, RefreshCw, Monitor, AlertTriangle, CheckCircle } from 'lucide-react';

export default function Maintenance() {
  const plans = [
    {
      name: "Basic",
      price: "$99",
      period: "/month",
      features: [
        "Security Updates",
        "Performance Monitoring",
        "Monthly Reports",
        "Email Support"
      ],
      popular: false
    },
    {
      name: "Professional",
      price: "$199",
      period: "/month",
      features: [
        "All Basic Features",
        "Daily Backups",
        "Content Updates",
        "Priority Support",
        "Performance Optimization"
      ],
      popular: true
    },
    {
      name: "Enterprise",
      price: "$299",
      period: "/month",
      features: [
        "All Professional Features",
        "Real-time Monitoring",
        "Advanced Security",
        "Dedicated Support",
        "Custom Development Hours"
      ],
      popular: false
    }
  ];

  const benefits = [
    {
      icon: <Shield className="w-8 h-8 text-blue-600" />,
      title: "Security",
      description: "Regular security updates and monitoring to protect your website."
    },
    {
      icon: <Monitor className="w-8 h-8 text-blue-600" />,
      title: "Performance",
      description: "Optimization for speed and performance to improve user experience."
    },
    {
      icon: <RefreshCw className="w-8 h-8 text-blue-600" />,
      title: "Updates",
      description: "Regular updates to keep your site current and secure."
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Website Maintenance Plans - WebDev Pro</title>
        <meta name="description" content="Comprehensive website maintenance plans to keep your website secure, up-to-date, and performing optimally." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Website Maintenance Plans</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            Keep your website secure, up-to-date, and performing at its best with our comprehensive maintenance plans.
          </p>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center mb-16">
          <div>
            <h2 className="text-3xl font-bold text-gray-900 mb-6">Why Website Maintenance Matters</h2>
            <p className="text-gray-600 mb-6">
              Your website needs regular care to stay secure, fast, and effective. Our maintenance plans ensure your site remains in top condition without the hassle.
            </p>
            <ul className="space-y-4">
              {benefits.map((benefit, index) => (
                <li key={index} className="flex items-start">
                  <div className="mt-1 mr-3">
                    {benefit.icon}
                  </div>
                  <div>
                    <h3 className="font-bold text-gray-900">{benefit.title}</h3>
                    <p className="text-gray-600">{benefit.description}</p>
                  </div>
                </li>
              ))}
            </ul>
          </div>
          <div className="bg-gray-100 rounded-xl p-8">
            <img 
              src="https://placehold.co/600x400/10b981/white?text=Website+Maintenance" 
              alt="Website Maintenance" 
              className="w-full h-64 object-cover rounded-lg"
            />
          </div>
        </div>

        <div className="text-center mb-12">
          <h2 className="text-3xl font-bold text-gray-900 mb-4">Choose Your Plan</h2>
          <p className="text-xl text-gray-600 max-w-2xl mx-auto">
            Select the maintenance plan that best fits your website's needs and budget.
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-3 gap-8 mb-16">
          {plans.map((plan, index) => (
            <div key={index} className={`bg-white rounded-xl shadow-lg border-2 ${plan.popular ? 'border-blue-500' : 'border-gray-200'} p-8 relative`}>
              {plan.popular && (
                <div className="absolute -top-4 left-1/2 transform -translate-x-1/2">
                  <span className="bg-blue-500 text-white px-4 py-1 rounded-full text-sm font-medium">
                    Most Popular
                  </span>
                </div>
              )}
              <h3 className="text-2xl font-bold text-center mb-4">{plan.name}</h3>
              <div className="text-center mb-6">
                <span className="text-4xl font-bold text-gray-900">{plan.price}</span>
                <span className="text-gray-600">{plan.period}</span>
              </div>
              <ul className="space-y-3 mb-8">
                {plan.features.map((feature, idx) => (
                  <li key={idx} className="flex items-center">
                    <CheckCircle className="w-5 h-5 text-green-500 mr-2" />
                    {feature}
                  </li>
                ))}
              </ul>
              <button className={`w-full py-3 px-4 rounded-lg font-medium ${
                plan.popular 
                  ? 'bg-blue-600 text-white hover:bg-blue-700' 
                  : 'bg-gray-100 text-gray-900 hover:bg-gray-200'
              }`}>
                Get Started
              </button>
            </div>
          ))}
        </div>

        <div className="bg-gradient-to-r from-blue-600 to-purple-700 rounded-2xl p-12 text-white text-center">
          <h2 className="text-3xl font-bold mb-4">Ready to Protect Your Website?</h2>
          <p className="text-xl mb-8 max-w-2xl mx-auto">
            Choose a maintenance plan today and let us handle the technical details.
          </p>
          <Link href="/contact" className="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg text-lg hover:bg-gray-100 transition-colors inline-block">
            Contact Us
          </Link>
        </div>
      </div>
    </div>
  );
}

// pages/marketing.js
import Head from 'next/head';
import Link from 'next/link';
import { Users, TrendingUp, Target, BarChart3, Mail, Share2 } from 'lucide-react';

export default function Marketing() {
  const services = [
    {
      icon: <Target className="w-8 h-8 text-blue-600" />,
      title: "Lead Generation",
      description: "Strategic campaigns to attract qualified prospects to your business."
    },
    {
      icon: <TrendingUp className="w-8 h-8 text-blue-600" />,
      title: "SEO Optimization",
      description: "Improve your search engine rankings and organic visibility."
    },
    {
      icon: <Mail className="w-8 h-8 text-blue-600" />,
      title: "Email Marketing",
      description: "Automated campaigns to nurture leads and retain customers."
    },
    {
      icon: <Share2 className="w-8 h-8 text-blue-600" />,
      title: "Social Media",
      description: "Engage your audience across all social platforms."
    }
  ];

  const results = [
    { metric: "Lead Increase", value: "150%" },
    { metric: "Conversion Rate", value: "25%" },
    { metric: "ROI", value: "400%" },
    { metric: "Customer Retention", value: "80%" }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Lead Sourcing & Marketing - WebDev Pro</title>
        <meta name="description" content="Strategic marketing solutions to generate qualified leads and grow your business." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Lead Sourcing & Marketing</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            Strategic marketing solutions to generate qualified leads and grow your business sustainably.
          </p>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center mb-16">
          <div>
            <h2 className="text-3xl font-bold text-gray-900 mb-6">Transform Your Lead Generation</h2>
            <p className="text-gray-600 mb-6">
              Our data-driven marketing strategies help you attract, convert, and retain high-quality leads that drive business growth.
            </p>
            <ul className="space-y-4">
              {services.map((service, index) => (
                <li key={index} className="flex items-start">
                  <div className="mt-1 mr-3">
                    {service.icon}
                  </div>
                  <div>
                    <h3 className="font-bold text-gray-900">{service.title}</h3>
                    <p className="text-gray-600">{service.description}</p>
                  </div>
                </li>
              ))}
            </ul>
          </div>
          <div className="bg-gray-100 rounded-xl p-8">
            <img 
              src="https://placehold.co/600x400/8b5cf6/white?text=Marketing+Strategy" 
              alt="Marketing Strategy" 
              className="w-full h-64 object-cover rounded-lg"
            />
          </div>
        </div>

        <div className="mb-16">
          <h2 className="text-3xl font-bold text-center text-gray-900 mb-12">Proven Results</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
            {results.map((result, index) => (
              <div key={index} className="bg-white p-6 rounded-xl shadow-lg text-center">
                <h3 className="text-3xl font-bold text-blue-600 mb-2">{result.value}</h3>
                <p className="text-gray-600">{result.metric}</p>
              </div>
            ))}
          </div>
        </div>

        <div className="bg-gradient-to-r from-blue-600 to-purple-700 rounded-2xl p-12 text-white text-center">
          <h2 className="text-3xl font-bold mb-4">Ready to Grow Your Business?</h2>
          <p className="text-xl mb-8 max-w-2xl mx-auto">
            Contact us today to discuss your marketing strategy and lead generation goals.
          </p>
          <Link href="/contact" className="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg text-lg hover:bg-gray-100 transition-colors inline-block">
            Get Started
          </Link>
        </div>
      </div>
    </div>
  );
}

// pages/portfolio.js
import Head from 'next/head';
import Link from 'next/link';
import { Code, Globe, Smartphone, Monitor } from 'lucide-react';

export default function Portfolio() {
  const projects = [
    {
      title: "E-commerce Platform",
      category: "Web App",
      description: "Custom e-commerce solution with inventory management and payment integration.",
      image: "https://placehold.co/600x400/3b82f6/white?text=E-commerce+Platform",
      beforeAfter: {
        before: "https://placehold.co/300x200/ef4444/white?text=Before",
        after: "https://placehold.co/300x200/22c55e/white?text=After"
      },
      results: [
        "50% increase in conversion rate",
        "200% improvement in page load speed",
        "150% growth in monthly revenue"
      ]
    },
    {
      title: "SaaS Dashboard",
      category: "Web App",
      description: "Analytics dashboard with real-time data visualization.",
      image: "https://placehold.co/600x400/8b5cf6/white?text=SaaS+Dashboard",
      beforeAfter: {
        before: "https://placehold.co/300x200/ef4444/white?text=Before",
        after: "https://placehold.co/300x200/22c55e/white?text=After"
      },
      results: [
        "30% increase in user engagement",
        "40% reduction in support tickets",
        "60% faster data processing"
      ]
    },
    {
      title: "Corporate Website",
      category: "Website",
      description: "Modern corporate website with CMS integration.",
      image: "https://placehold.co/600x400/10b981/white?text=Corporate+Site",
      beforeAfter: {
        before: "https://placehold.co/300x200/ef4444/white?text=Before",
        after: "https://placehold.co/300x200/22c55e/white?text=After"
      },
      results: [
        "70% increase in lead generation",
        "25% improvement in SEO ranking",
        "80% faster page load times"
      ]
    },
    {
      title: "Mobile Banking App",
      category: "Mobile App",
      description: "Secure mobile banking application with biometric authentication.",
      image: "https://placehold.co/600x400/f59e0b/white?text=Banking+App",
      beforeAfter: {
        before: "https://placehold.co/300x200/ef4444/white?text=Before",
        after: "https://placehold.co/300x200/22c55e/white?text=After"
      },
      results: [
        "45% increase in active users",
        "90% satisfaction rating",
        "99.9% uptime reliability"
      ]
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Portfolio - WebDev Pro</title>
        <meta name="description" content="View our portfolio of web development projects and case studies." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Our Portfolio</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            Explore our collection of successful projects and see how we've helped businesses transform their digital presence.
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">
          {projects.map((project, index) => (
            <div key={index} className="bg-white rounded-xl shadow-lg overflow-hidden">
              <img 
                src={project.image} 
                alt={project.title} 
                className="w-full h-48 object-cover"
              />
              <div className="p-6">
                <span className="text-sm text-blue-600 font-medium">{project.category}</span>
                <h3 className="text-xl font-bold mt-2 mb-2">{project.title}</h3>
                <p className="text-gray-600 mb-4">{project.description}</p>
                
                <div className="flex gap-2 mb-4">
                  <div className="flex flex-col items-center">
                    <span className="text-xs text-gray-500 mb-1">Before</span>
                    <img src={project.beforeAfter.before} alt="Before" className="w-12 h-8 object-cover rounded" />
                  </div>
                  <div className="flex flex-col items-center">
                    <span className="text-xs text-gray-500 mb-1">After</span>
                    <img src={project.beforeAfter.after} alt="After" className="w-12 h-8 object-cover rounded" />
                  </div>
                </div>
                
                <div className="mb-4">
                  <h4 className="font-bold text-gray-900 mb-2">Results:</h4>
                  <ul className="space-y-1">
                    {project.results.map((result, idx) => (
                      <li key={idx} className="text-sm text-gray-600 flex items-center">
                        <div className="w-2 h-2 bg-green-500 rounded-full mr-2"></div>
                        {result}
                      </li>
                    ))}
                  </ul>
                </div>
                
                <Link href={`/case-study/${index}`} className="text-blue-600 font-medium hover:text-blue-800 flex items-center">
                  View Full Case Study <ChevronRight size={16} className="ml-1" />
                </Link>
              </div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}

// pages/about.js
import Head from 'next/head';
import Link from 'next/link';
import { Users, Award, Clock, CheckCircle } from 'lucide-react';

export default function About() {
  const stats = [
    { value: "150+", label: "Projects Completed" },
    { value: "98%", label: "Client Satisfaction" },
    { value: "50+", label: "Happy Clients" },
    { value: "5", label: "Years Experience" }
  ];

  const team = [
    {
      name: "John Smith",
      role: "Founder & Lead Developer",
      bio: "10+ years experience in web development and team leadership.",
      image: "https://placehold.co/200x200/3b82f6/white?text=JS"
    },
    {
      name: "Sarah Johnson",
      role: "Creative Director",
      bio: "Expert in UI/UX design with a passion for user-centered solutions.",
      image: "https://placehold.co/200x200/8b5cf6/white?text=SJ"
    },
    {
      name: "Michael Chen",
      role: "Marketing Specialist",
      bio: "Digital marketing expert focused on lead generation and growth.",
      image: "https://placehold.co/200x200/10b981/white?text=MC"
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>About Us - WebDev Pro</title>
        <meta name="description" content="Learn about WebDev Pro, our team, mission, and values." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">About WebDev Pro</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            We're a team of passionate developers and designers dedicated to helping businesses succeed online.
          </p>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center mb-16">
          <div>
            <h2 className="text-3xl font-bold text-gray-900 mb-6">Our Mission</h2>
            <p className="text-gray-600 mb-6">
              At WebDev Pro, we believe every business deserves a powerful digital presence. Our mission is to empower businesses with custom web solutions that drive growth, improve user experience, and achieve measurable results.
            </p>
            <p className="text-gray-600 mb-6">
              We combine technical expertise with strategic thinking to deliver solutions that not only look great but also perform exceptionally well.
            </p>
            <div className="space-y-4">
              <div className="flex items-start">
                <CheckCircle className="w-6 h-6 text-green-500 mt-1 mr-3" />
                <div>
                  <h3 className="font-bold text-gray-900">Client-Centric Approach</h3>
                  <p className="text-gray-600">We prioritize your goals and vision in every project.</p>
                </div>
              </div>
              <div className="flex items-start">
                <CheckCircle className="w-6 h-6 text-green-500 mt-1 mr-3" />
                <div>
                  <h3 className="font-bold text-gray-900">Quality Assurance</h3>
                  <p className="text-gray-600">Rigorous testing ensures reliable and bug-free solutions.</p>
                </div>
              </div>
              <div className="flex items-start">
                <CheckCircle className="w-6 h-6 text-green-500 mt-1 mr-3" />
                <div>
                  <h3 className="font-bold text-gray-900">Continuous Support</h3>
                  <p className="text-gray-600">Ongoing maintenance and support for long-term success.</p>
                </div>
              </div>
            </div>
          </div>
          <div className="bg-gray-100 rounded-xl p-8">
            <img 
              src="https://placehold.co/600x400/3b82f6/white?text=About+Us" 
              alt="About Us" 
              className="w-full h-64 object-cover rounded-lg"
            />
          </div>
        </div>

        <div className="mb-16">
          <h2 className="text-3xl font-bold text-center text-gray-900 mb-12">Our Numbers</h2>
          <div className="grid grid-cols-2 md:grid-cols-4 gap-8">
            {stats.map((stat, index) => (
              <div key={index} className="text-center">
                <div className="text-3xl font-bold text-blue-600 mb-2">{stat.value}</div>
                <div className="text-gray-600">{stat.label}</div>
              </div>
            ))}
          </div>
        </div>

        <div className="mb-16">
          <h2 className="text-3xl font-bold text-center text-gray-900 mb-12">Meet Our Team</h2>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {team.map((member, index) => (
              <div key={index} className="text-center">
                <img 
                  src={member.image} 
                  alt={member.name} 
                  className="w-32 h-32 rounded-full mx-auto mb-4"
                />
                <h3 className="text-xl font-bold text-gray-900">{member.name}</h3>
                <p className="text-blue-600 mb-2">{member.role}</p>
                <p className="text-gray-600">{member.bio}</p>
              </div>
            ))}
          </div>
        </div>

        <div className="bg-gradient-to-r from-blue-600 to-purple-700 rounded-2xl p-12 text-white text-center">
          <h2 className="text-3xl font-bold mb-4">Ready to Work Together?</h2>
          <p className="text-xl mb-8 max-w-2xl mx-auto">
            Let's discuss how we can help your business grow online.
          </p>
          <Link href="/contact" className="bg-white text-blue-600 font-bold py-3 px-8 rounded-lg text-lg hover:bg-gray-100 transition-colors inline-block">
            Get Started
          </Link>
        </div>
      </div>
    </div>
  );
}

// pages/contact.js
import Head from 'next/head';
import Link from 'next/link';
import { Mail, Phone, MapPin, Send, CheckCircle } from 'lucide-react';

export default function Contact() {
  const [formData, setFormData] = useState({
    name: '',
    email: '',
    phone: '',
    message: ''
  });
  const [submitted, setSubmitted] = useState(false);

  const handleChange = (e) => {
    setFormData({
      ...formData,
      [e.target.name]: e.target.value
    });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    // In a real app, you would send this data to your backend
    console.log('Form submitted:', formData);
    setSubmitted(true);
    setFormData({ name: '', email: '', phone: '', message: '' });
  };

  const contactInfo = [
    {
      icon: <Mail className="w-6 h-6" />,
      title: "Email",
      value: "contact@webdevpro.com",
      description: "Send us a message anytime"
    },
    {
      icon: <Phone className="w-6 h-6" />,
      title: "Phone",
      value: "(555) 123-4567",
      description: "Mon-Fri from 9am to 5pm"
    },
    {
      icon: <MapPin className="w-6 h-6" />,
      title: "Office",
      value: "San Francisco, CA",
      description: "Visit us in person"
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Contact Us - WebDev Pro</title>
        <meta name="description" content="Get in touch with WebDev Pro for web development services." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Contact Us</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            Have a project in mind? We'd love to hear about it. Get in touch with us today.
          </p>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-2 gap-12">
          <div>
            <h2 className="text-2xl font-bold text-gray-900 mb-6">Send us a message</h2>
            {submitted ? (
              <div className="bg-green-50 border border-green-200 rounded-lg p-6 text-center">
                <CheckCircle className="w-12 h-12 text-green-500 mx-auto mb-4" />
                <h3 className="text-xl font-bold text-green-800 mb-2">Message Sent!</h3>
                <p className="text-green-700">
                  Thank you for your message. We'll get back to you as soon as possible.
                </p>
              </div>
            ) : (
              <form onSubmit={handleSubmit} className="space-y-6">
                <div>
                  <label htmlFor="name" className="block text-sm font-medium text-gray-700 mb-1">
                    Full Name
                  </label>
                  <input
                    type="text"
                    id="name"
                    name="name"
                    value={formData.name}
                    onChange={handleChange}
                    required
                    className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                    placeholder="Your full name"
                  />
                </div>
                <div>
                  <label htmlFor="email" className="block text-sm font-medium text-gray-700 mb-1">
                    Email Address
                  </label>
                  <input
                    type="email"
                    id="email"
                    name="email"
                    value={formData.email}
                    onChange={handleChange}
                    required
                    className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                    placeholder="your.email@example.com"
                  />
                </div>
                <div>
                  <label htmlFor="phone" className="block text-sm font-medium text-gray-700 mb-1">
                    Phone Number
                  </label>
                  <input
                    type="tel"
                    id="phone"
                    name="phone"
                    value={formData.phone}
                    onChange={handleChange}
                    className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                    placeholder="(555) 123-4567"
                  />
                </div>
                <div>
                  <label htmlFor="message" className="block text-sm font-medium text-gray-700 mb-1">
                    Message
                  </label>
                  <textarea
                    id="message"
                    name="message"
                    value={formData.message}
                    onChange={handleChange}
                    required
                    rows={5}
                    className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                    placeholder="Tell us about your project..."
                  />
                </div>
                <button
                  type="submit"
                  className="w-full bg-blue-600 text-white font-bold py-3 px-6 rounded-lg hover:bg-blue-700 transition-colors flex items-center justify-center"
                >
                  <Send className="w-5 h-5 mr-2" />
                  Send Message
                </button>
              </form>
            )}
          </div>
          
          <div>
            <h2 className="text-2xl font-bold text-gray-900 mb-6">Contact Information</h2>
            <div className="space-y-6">
              {contactInfo.map((info, index) => (
                <div key={index} className="flex items-start p-4 border border-gray-200 rounded-lg">
                  <div className="text-blue-600 mr-4 mt-1">
                    {info.icon}
                  </div>
                  <div>
                    <h3 className="font-bold text-gray-900">{info.title}</h3>
                    <p className="text-gray-600 font-medium">{info.value}</p>
                    <p className="text-gray-500 text-sm">{info.description}</p>
                  </div>
                </div>
              ))}
            </div>
            
            <div className="mt-8">
              <h3 className="text-xl font-bold text-gray-900 mb-4">Our Location</h3>
              <div className="bg-gray-200 rounded-lg h-64 flex items-center justify-center">
                <div className="text-center text-gray-500">
                  <MapPin className="w-12 h-12 mx-auto mb-2" />
                  <p>Interactive Map</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}

// pages/blog.js
import Head from 'next/head';
import Link from 'next/link';
import { Calendar, User, Tag } from 'lucide-react';

export default function Blog() {
  const posts = [
    {
      title: "The Future of Web Development: Trends to Watch in 2025",
      excerpt: "Explore the emerging technologies and trends that will shape the future of web development.",
      date: "November 15, 2025",
      author: "John Smith",
      tags: ["Web Development", "Technology", "Trends"],
      image: "https://placehold.co/600x300/3b82f6/white?text=Web+Development"
    },
    {
      title: "How to Choose the Right CMS for Your Business",
      excerpt: "A comprehensive guide to selecting the best content management system for your website needs.",
      date: "November 10, 2025",
      author: "Sarah Johnson",
      tags: ["CMS", "Web Design", "Business"],
      image: "https://placehold.co/600x300/8b5cf6/white?text=CMS+Guide"
    },
    {
      title: "Maximizing Your ROI with Strategic Web Design",
      excerpt: "Learn how strategic web design decisions can significantly impact your business's bottom line.",
      date: "November 5, 2025",
      author: "Michael Chen",
      tags: ["Web Design", "ROI", "Marketing"],
      image: "https://placehold.co/600x300/10b981/white?text=ROI+Strategy"
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Blog - WebDev Pro</title>
        <meta name="description" content="Latest insights and tips on web development, design, and digital marketing." />
      </Head>

      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div className="text-center mb-16">
          <h1 className="text-4xl font-bold text-gray-900 mb-4">Our Blog</h1>
          <p className="text-xl text-gray-600 max-w-3xl mx-auto">
            Latest insights, tips, and industry trends on web development, design, and digital marketing.
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          {posts.map((post, index) => (
            <article key={index} className="bg-white rounded-xl shadow-lg overflow-hidden">
              <img 
                src={post.image} 
                alt={post.title} 
                className="w-full h-48 object-cover"
              />
              <div className="p-6">
                <div className="flex items-center text-sm text-gray-500 mb-3">
                  <Calendar className="w-4 h-4 mr-1" />
                  <span>{post.date}</span>
                  <User className="w-4 h-4 ml-4 mr-1" />
                  <span>{post.author}</span>
                </div>
                <h2 className="text-xl font-bold text-gray-900 mb-3">{post.title}</h2>
                <p className="text-gray-600 mb-4">{post.excerpt}</p>
                <div className="flex flex-wrap gap-2 mb-4">
                  {post.tags.map((tag, idx) => (
                    <span key={idx} className="bg-blue-100 text-blue-800 text-xs px-2 py-1 rounded">
                      {tag}
                    </span>
                  ))}
                </div>
                <Link href={`/blog/${index}`} className="text-blue-600 font-medium hover:text-blue-800">
                  Read More →
                </Link>
              </div>
            </article>
          ))}
        </div>
      </div>
    </div>
  );
}

// pages/privacy-policy.js
import Head from 'next/head';
import Link from 'next/link';

export default function PrivacyPolicy() {
  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Privacy Policy - WebDev Pro</title>
        <meta name="description" content="Privacy policy for WebDev Pro." />
      </Head>

      <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <h1 className="text-4xl font-bold text-gray-900 mb-8">Privacy Policy</h1>
        
        <div className="prose max-w-none">
          <p className="mb-4">
            <strong>Last Updated:</strong> November 25, 2025
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Introduction</h2>
          <p className="mb-4">
            WebDev Pro ("we", "us", or "our") operates the website and provides web development services. This page informs you of our policies regarding the collection, use, and disclosure of personal data when you use our service and the choices you have associated with that data.
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Information Collection and Use</h2>
          <p className="mb-4">
            We collect several different types of information for various purposes to provide and improve our service to you.
          </p>
          
          <h3 className="text-xl font-bold text-gray-900 mb-2">Types of Data Collected</h3>
          <h4 className="text-lg font-bold text-gray-900 mb-2">Personal Data</h4>
          <p className="mb-4">
            While using our service, we may ask you to provide us with certain personally identifiable information that can be used to contact or identify you ("Personal Data"). Personally identifiable information may include, but is not limited to:
          </p>
          <ul className="list-disc list-inside mb-4">
            <li>Email address</li>
            <li>First name and last name</li>
            <li>Phone number</li>
            <li>Address, State, Province, ZIP/Postal code</li>
            <li>Cookies and usage data</li>
          </ul>
          
          <h4 className="text-lg font-bold text-gray-900 mb-2">Usage Data</h4>
          <p className="mb-4">
            We may also collect information that your browser sends whenever you visit our service or when you access the service by or through a mobile device ("Usage Data").
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Use of Data</h2>
          <p className="mb-4">
            WebDev Pro uses the collected data for various purposes:
          </p>
          <ul className="list-disc list-inside mb-4">
            <li>To provide and maintain our service</li>
            <li>To notify you about changes to our service</li>
            <li>To provide customer support</li>
            <li>To gather analysis or valuable information so that we can improve our service</li>
            <li>To monitor the usage of our service</li>
            <li>To detect, prevent, and address technical issues</li>
          </ul>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Security of Data</h2>
          <p className="mb-4">
            The security of your data is important to us, but remember that no method of transmission over the Internet, or method of electronic storage is 100% secure. While we strive to use commercially acceptable means to protect your Personal Data, we cannot guarantee its absolute security.
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Service Providers</h2>
          <p className="mb-4">
            We may employ third-party companies and individuals due to the following reasons:
          </p>
          <ul className="list-disc list-inside mb-4">
            <li>To facilitate our service</li>
            <li>To provide the service on our behalf</li>
            <li>To perform service-related services</li>
            <li>To assist us in analyzing how our service is used</li>
          </ul>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Changes to This Privacy Policy</h2>
          <p className="mb-4">
            We may update our Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy on this page.
          </p>
          <p className="mb-4">
            You are advised to review this Privacy Policy periodically for any changes. Changes to this Privacy Policy are effective when they are posted on this page.
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Contact Us</h2>
          <p className="mb-4">
            If you have any questions about this Privacy Policy, please contact us:
          </p>
          <ul className="list-disc list-inside mb-4">
            <li>By email: privacy@webdevpro.com</li>
          </ul>
        </div>
      </div>
    </div>
  );
}

// pages/terms-and-conditions.js
import Head from 'next/head';
import Link from 'next/link';

export default function TermsAndConditions() {
  return (
    <div className="min-h-screen bg-white">
      <Head>
        <title>Terms & Conditions - WebDev Pro</title>
        <meta name="description" content="Terms and conditions for WebDev Pro services." />
      </Head>

      <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <h1 className="text-4xl font-bold text-gray-900 mb-8">Terms and Conditions</h1>
        
        <div className="prose max-w-none">
          <p className="mb-4">
            <strong>Last Updated:</strong> November 25, 2025
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Introduction</h2>
          <p className="mb-4">
            These terms and conditions ("Terms", "Terms and Conditions") govern your relationship with the WebDev Pro website and services (the "Service") operated by WebDev Pro.
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Interpretation and Definitions</h2>
          <h3 className="text-xl font-bold text-gray-900 mb-2">Interpretation</h3>
          <p className="mb-4">
            The words of which the initial letter is capitalized have meanings defined under the following conditions. The following definitions shall have the same meaning regardless of whether they appear in singular or in plural.
          </p>
          
          <h3 className="text-xl font-bold text-gray-900 mb-2">Definitions</h3>
          <p className="mb-4">
            For the purposes of these Terms and Conditions:
          </p>
          <ul className="list-disc list-inside mb-4">
            <li><strong>Company</strong> (referred to as either "the Company", "We", "Us" or "Our" in this Agreement) refers to WebDev Pro.</li>
            <li><strong>Service</strong> refers to the Website.</li>
            <li><strong>Country</strong> refers to: California, United States</li>
            <li><strong>Service Provider</strong> means any natural or legal person who processes the data on behalf of the Company.</li>
            <li><strong>Account</strong> means a unique account created for You to access our Service or parts of our Service.</li>
            <li><strong>Website</strong> refers to WebDev Pro, accessible from https://webdevpro.com</li>
          </ul>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Acknowledgment</h2>
          <p className="mb-4">
            These are the Terms and Conditions governing the use of this Service and the agreement that operates between You and the Company. These Terms and Conditions set out the rights and obligations of all users regarding the use of the Service.
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Use License</h2>
          <p className="mb-4">
            Unless otherwise stated, the Company and/or its licensors own the intellectual property rights for all material on the Service. All intellectual property rights are reserved. You may access this from the Service for your own personal use subjected to restrictions set in these terms and conditions.
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Prohibited Uses</h2>
          <p className="mb-4">
            You are specifically restricted from all of the following:
          </p>
          <ul className="list-disc list-inside mb-4">
            <li>publishing any Service material in any other media</li>
            <li>selling, sublicensing and/or otherwise commercializing any Service material</li>
            <li>publicly performing and/or showing any Service material</li>
            <li>using this Service in any way that is or may be damaging to this Service</li>
            <li>using this Service in any way that impacts user access to this Service</li>
          </ul>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Limitation of Liability</h2>
          <p className="mb-4">
            To the maximum extent permitted by applicable law, in no event shall the Company, nor its suppliers, be liable for any special, incidental, indirect, or consequential damages whatsoever (including, but not limited to, damages for loss of profits, loss of data or other information, for business interruption, for personal injury, loss of privacy arising out of or in any way related to the use of or inability to use the Service).
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Changes to These Terms and Conditions</h2>
          <p className="mb-4">
            We reserve the right, at our sole discretion, to modify or replace these Terms at any time. If a revision is material we will try to provide at least 30 days' notice prior to any new terms taking effect. What constitutes a material change will be determined at our sole discretion.
          </p>
          
          <h2 className="text-2xl font-bold text-gray-900 mb-4">Contact Us</h2>
          <p className="mb-4">
            If you have any questions about these Terms and Conditions, please contact us:
          </p>
          <ul className="list-disc list-inside mb-4">
            <li>By email: legal@webdevpro.com</li>
          </ul>
        </div>
      </div>
    </div>
  );
}
