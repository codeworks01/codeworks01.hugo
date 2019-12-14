+++
authors = []
date = 2019-12-14T05:00:00Z
draft = true
excerpt = ""
hero = "/uploads/cnc-laser-cutting-of-metal-modern-industrial-Y9JC5U6.jpg"
timeToRead = nil
title = "code"

+++
# Hello

    ```js
    import React from "react";
    import { graphql, useStaticQuery } from "gatsby";
    import styled from "@emotion/styled";
    
    import * as SocialIcons from "../../icons/social";
    import mediaqueries from "@styles/media";
    
    const icons = {
      dribbble: SocialIcons.DribbbleIcon,
      linkedin: SocialIcons.LinkedinIcon,
      twitter: SocialIcons.TwitterIcon,
      facebook: SocialIcons.FacebookIcon,
      instagram: SocialIcons.InstagramIcon,
      github: SocialIcons.GithubIcon,
    };
    
    const socialQuery = graphql`
      {
        allSite {
          edges {
            node {
              siteMetadata {
                social {
                  name
                  url
                }
              }
            }
          }
        }
      }
    `;
    
    function SocialLinks({ fill = "#73737D" }: { fill: string }) {
      const result = useStaticQuery(socialQuery);
      const socialOptions = result.allSite.edges[0].node.siteMetadata.social;
    
      return (
        <>
          {socialOptions.map(option => {
            const Icon = icons[option.name];
    
            return (
              <SocialIconContainer
                key={option.name}
                target="_blank"
                rel="noopener"
                data-a11y="false"
                aria-label={`Link to ${option.name}`}
                href={option.url}
              >
                <Icon fill={fill} />
              </SocialIconContainer>
            );
          })}
        </>
      );
    }
    ```